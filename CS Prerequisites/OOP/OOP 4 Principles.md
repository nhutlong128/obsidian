# Encapsulation
- [[Encapsulation]]: Object state, properties are "packaged" within an object => There is a protection on these state, properties => Encapsulation
- Object state or Object properties can only be managed and accessed by it's object through Object method => These state, properties can't be managed and accessed by other Object
- Example: If there is no [[Encapsulation]], the money of customer A will be withdrawed from customer B

# Abstraction
- [[Abstraction]]: is purposeful hiding of some details of a progress
- One object contains so many methods but the user may only needs 1 or 2 => [[Abstraction]] helps the object expose the most high level mechanism for using it
- Example: Delete method may needs any underlying helper methods, but the user only needs to know the presence of Delete method, not other methods in Object
# Inheritance
- [[Inheritance]] helps many object shares the common logic (but not the same)
- Example: The rectangular object and the square object both inherit the shape object


# Polymorphism
- [[Polymorphism]] means "many shapes" in Greek. A shape can has this "shape" but the other can have that "shape" but overall they are shape all the same.
- Example: All the animal can 'say', but depend on it's type it can have different way to 'say'. Dog say 'bard', Cat say 'meow',... These object have the same 'say' method, but the implementation is different 