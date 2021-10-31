# Software Definitions

- This is page include to some of software definitions to review your memory

# Inheritance and Composition

## Inheritance: 

- When we want to create a new class and there is already a class that includes some of the code that we want, we can derive our new class from the existing class. In doing this, we can reuse the fields and methods of the existing class without having to write them ourself.

- A subclass inherits all the members (fields, methods, and nested classes) from its superclass. Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.

```jave
class A {
    int a, b;
    public void add(int x, int y)
    {
        a = x;
        b = y;
        System.out.println(
            "addition of a + b is:"
            + (a + b));
    }
}
 
class B extends A {
    public void sum(int x, int y)
    {
        add(x, y);
    }
 
    // Driver Code
    public static void main(String[] args)
    {
        B b1 = new B();
        b1.sum(5, 6);
    }
}

// Output: 
// addition of a+b is:11 

```
- Here, class B is the derived class which inherit the property(add method) of the base class A.

## Composition: 
 - The composition also provides code reusability but the difference here is we do not extend the class for this.
 
 ```jave
 import java.io.*;
 import java.util.*;
  
 // class book
 class Book {
  
     public String title;
     public String author;
  
     Book(String title, String author)
     {
  
         this.title = title;
         this.author = author;
     }
 }
  
 // Library class contains
 // list of books.
 class Library {
  
     // reference to refer to the list of books.
     private final List<Book> books;
  
     Library(List<Book> books)
     {
         this.books = books;
     }
  
     public List<Book> getTotalBooksInLibrary()
     {
  
         return books;
     }
 }
  
 // main method
 class GFG {
     public static void main(String[] args)
     {
  
         // Creating the Objects of Book class.
         Book b1 = new Book(
             "EffectiveJ Java",
             "Joshua Bloch");
         Book b2 = new Book(
             "Thinking in Java",
             "Bruce Eckel");
         Book b3 = new Book(
             "Java: The Complete Reference",
             "Herbert Schildt");
  
         // Creating the list which contains the
         // no. of books.
         List<Book> books = new ArrayList<Book>();
         books.add(b1);
         books.add(b2);
         books.add(b3);
  
         Library library = new Library(books);
  
         List<Book> bks = library.getTotalBooksInLibrary();
         for (Book bk : bks) {
  
             System.out.println("Title : "
                                + bk.title + " and "
                                + " Author : "
                                + bk.author);
         }
     }
 }
 
 // Output:
 
 // Title : EffectiveJ Java and  Author : Joshua Bloch
 // Title : Thinking in Java and  Author : Bruce Eckel
 // Title : Java: The Complete Reference and  Author : Herbert Schildt
 
 ```

## Difference between Inheritance and Composition:

| S.NO  | Inheritance | Composition
| ------------- | ------------- | ------------- |
| 1.  | In inheritance, we define the class which we are inheriting(super class) and most importantly it cannot be changed at runtime  | Whereas in composition we only define a type which we want to use and which can hold its different implementation also it can change at runtime. Hence, Composition is much more flexible than Inheritance. | 
| 2.  | Here we can only extend one class, in other words more than one class can’t be extended as java do not support multiple inheritance.   | Whereas composition allows to use functionality from different class. |
| 3. | In inheritance we need parent class in order to test child class. | Composition allows to test the implementation of the classes we are using independent of parent or child class. |

| 4. | Inheritance cannot extend final class.  | Whereas composition allows code reuse even from final classes. |

| 5. | It is an is-a relationship.  | While it is a has-a relationship. |
