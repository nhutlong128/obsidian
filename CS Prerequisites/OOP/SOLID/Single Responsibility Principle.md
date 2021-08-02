# Definition
- A class should have only one job => Change the class if and only if one requirement changes
- Asking a simple question before you make any changes: What is the responsibility of your class/component/microservice? => If your answer includes the word “and”, you’re most likely breaking the single responsibility principle.

# Example
![[Pasted image 20210730152616.png]]
![[Pasted image 20210730152627.png]]
# Advantage
- Requirements change over time => The more responsibilities your class has, the more often you need to change it

# Warning
-  Some developers take the single responsibility principle to the extreme by creating classes with just one function