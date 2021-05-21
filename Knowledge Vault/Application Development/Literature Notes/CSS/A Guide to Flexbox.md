### Metadata

-  Type: #literature #flexbox
    Date written: [[2021-05-20, Thu]]  
    Source:  https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
    Status: #done  
    Keywords:  #applicationdevelopment #webapp #css #flexbox
	
### Notes
- The **main idea** behind the **flex layout** is to give the container the ability to **alter** its items’ width/height (and order) to **best fill** the available space (mostly to accommodate to all kind of display devices and screen sizes).
- ![[Pasted image 20210520163308.png]]
- ## Properties for the Parent  (flex container)
	- #### display
		- ![[Pasted image 20210520163350.png]]
	- #### flex-direction
		- Flexbox is (aside from optional wrapping) a single-direction layout concept.
		- ![[Pasted image 20210520163435.png]]
		- ![[Pasted image 20210520163448.png]]
	- #### flex-wrap
		- By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.
		- ![[Pasted image 20210520163613.png]]
		- ![[Pasted image 20210520163618.png]]
	- #### justify-content
		- ![[Pasted image 20210520164311.png]]
		- ![[Pasted image 20210520164329.png]]
	- #### align-items
		- ![[Pasted image 20210520164511.png]]
		- ![[Pasted image 20210520164517.png]]
	- #### align-content
		- ![[Pasted image 20210520164532.png]]
		- ![[Pasted image 20210520164538.png]]

- ## Properties for the Children (flex items)
	- #### flex-grow
		- ![[Pasted image 20210520164806.png]]
		- ![[Pasted image 20210520164812.png]]
		- If all items have `flex-grow` set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).
	- #### align-self
		- ![[Pasted image 20210520164842.png]]
		- This allows the default alignment (or the one specified by `align-items`) to be overridden for individual flex items.
		- ![[Pasted image 20210520164850.png]]