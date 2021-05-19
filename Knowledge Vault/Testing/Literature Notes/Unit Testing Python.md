### Metadata

-  Type: #literature #unittesting
    Date written: [[2021-05-18, Mon]]  
    Source:  https://medium.com/@yeraydiazdiaz/what-the-mock-cheatsheet-mocking-in-python-6a71db997832
    Status: #wip 
    Keywords:  #testing #python 
	
### Notes
- The main characteristic of a **Mock** object is that it will return another "Mock" instance when:
	- accessing one of its attributes
	- calling the object itself

-  You can assign a value to an **attribute** in the **Mock** by:
	-   Assign it directly, like you’d do with any Python object.
		 ```python
		m.foo = 'bar'
		```
	
	- Use the configure_mock** method on an instance.
		```python
		m.configure_mock(bar='baz')
		```
	-   Or pass keyword arguments to the **Mock** class on creation
		```python
		m = mock.Mock(bar='d')
		```

- To override **calls** to the mock you’ll need to:
	- configure its **return_value** property. The **Mock** will **always return the same value on all calls**
		```python
		m.return_value = 42
		assert m() == 42
		```
	- if you’d like to **return different values on each call** you can assign an iterable to **side_effect**
		```python
		m.side_effect = ['foo', 'bar', 'baz']
		assert m() == 'foo'
		assert m() == 'bar'
		assert m() == 'baz'
		```
	- If you’d like to **raise an exception** when calling the Mock you can simply assign the exception object to **side_effect**
		```python
		m.side\_effect \= RuntimeError('Boom')
		try:
			m()
		except RuntimeError:
			assert True
		else:
			assert False
		```

- The main way to use **unittest.mock** is to **patch imports in the module under test** using the **patch** function

- **patch** will intercept  **import** statements identified by a string, and return a **Mock** instance you can preconfigure.
	```python
	from unittest import TestCase, mock
	from work import work_on
	class TestWorkMockingModule(TestCase):
		def test_using_context_manager(self):
			with mock.patch('work.os') as mocked_os:
				work_on()
				mocked_os.getcwd.assert_called_once()
	```

- Alternatively, we can use the decorator version of `patch` , note this time the test has an extra parameter: `mocked_os` to which the `Mock` is injected into the test.
	```python
	@mock.patch('work.os')
	def test\_using\_decorator(self, mocked\_os):
		work\_on()
		mocked\_os.getcwd.assert\_called\_once()
	```
	
- `patch` will forward keyword arguments to the `Mock` class, so to configure a `return_value` we simply add it as one:
	```python
	def test\_using\_return\_value(self):
		with mock.patch('work.os.getcwd', return\_value\='testing'):
			assert work\_on() \== 'testing'
	```

- A consequence of the flexibility of `Mock` is that once we’ve mocked a class Python will not raise `AttributeError` as it simply will return new instances of `MagicMock` for basically everything. This is usually a good thing but can lead to some confusing behaviour and potentially bugs. For instance writing the following test:
	```python
	def test\_patching\_class\_with\_typo(self):
		with mock.patch('worker.Helper') as MockHelper:
			MockHelper.return\_value.get\_path.return\_value \= 'testing'
			worker \= Worker()
			MockHelper.assrt\_called\_once\_with('db') \# erm....
			self.assertEqual(worker.work(), 'testing')
	```
	- will silently pass with no warning completely missing the typo in `assrt_called_once`
- Put simply, it preconfigures mocks to only respond to methods that actually exist in the spec class. The easiest is to simply pass `[autospec=True]` to the `patch` call, which will configure the `Mock` to behave as the object being mocked, raising exceptions for missing attributes and incorrect signatures as required
	```python
	def test\_patching\_class\_with\_spec(self):
		with mock.patch('worker.Helper', autospec\=True) as MockHelper:
			\# the following would raise attribute error
			\# MockHelper.return\_value.get\_path.return\_value = 'testing'
			MockHelper.return\_value.get\_folder.return\_value \= 'testing'
			worker \= Worker()
			MockHelper.assert\_called\_once\_with('db')
			\# this test will fail since we we're still using \`get\_path\`
			self.assertEqual(worker.work(), 'testing')
	```

- `patch.``dict`(_in\_dict_, _values=()_, _clear=False_, _\*\*kwargs_): Patch a dictionary, or dictionary like object, and restore the dictionary to its original state after the test.
	```python
	foo \= {}
	@patch.dict(foo, {'newkey': 'newvalue'})
	def test():
		assert foo \== {'newkey': 'newvalue'}
	test()
	assert foo \== {}
	```
- If you’re not fond of nesting context managers you can also write the `patch` calls in the decorator form:
	```python
	@mock.patch('os.getcwd', return\_value\='/home/')
	@mock.patch('worker.print')
	@mock.patch.dict('os.environ', {'MY\_VAR': 'testing'})
	def test\_patch\_builtin\_dict\_decorators(self, mock\_print, mock\_getcwd):
		self.assertEqual(work\_on\_env(), '/home/testing')
		mock\_print.assert\_called\_once\_with('Working on /home/testing')
	```
- Mock a class attribute
	```python
	from unittest import TestCase, mock, expectedFailure
	from pricer import Pricer
	
	class TestClassAttribute(TestCase):
		def test\_patch\_instance\_attribute(self):
			pricer \= Pricer()
			pricer.DISCOUNT \= 0.5
			self.assertAlmostEqual(pricer.get\_discounted\_price(100), 50.0)
		
		def test\_set\_class\_attribute(self):
			Pricer.DISCOUNT \= 0.75
			pricer \= Pricer()
			self.assertAlmostEqual(pricer.get\_discounted\_price(100), 75.0)
		
		@expectedFailure
		def test\_patch\_incorrect\_class\_attribute(self):
			with mock.patch.object(Pricer, 'PERCENTAGE', 1):
				pricer \= Pricer()
				self.assertAlmostEqual(pricer.get\_discounted\_price(100), 100)
		
		def test\_patch\_class\_attribute(self):
			with mock.patch.object(Pricer, 'DISCOUNT', 1):
				pricer \= Pricer()
				self.assertAlmostEqual(pricer.get\_discounted\_price(100), 100)
	```
