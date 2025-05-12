1. Interfaces vs. Types: What’s the Difference?

Interfaces is mainly used to define the structure of an object. So, if we need to define the shape of an object we need interfaces. One the other hand type is like a tag that tells what kind of data it is.

In Interfaces we can add more properties to them or create a new one that builds from older one. But type can be extended but type can be combined using intersections type.

We use interface if we just need to describe objects or classes. We use types when we need more flexibility and working with other data.

Example:

interface Car {
  make: string;
  model: string;
}

interface Car {
  year: number;  
}

This gets automatically added to the first interface

But for type
type User = {
  name: string;
  age: number;
};

 type User =
  {   address: string;
};

This would cause an error because types can’t be declared twice.


2. What is the use of the keyof keyword in TypeScript? Provide an example.

keyof used to get the keys from an object. When we need to know or we want all the keys of an object we need keyof.It's like give me all the property names of an object.

When you need a valid key from an object not guessing it you can use keyof to get that.

Example: 

type Person = {
  name: string;
  age: number;
};

 keyof Person becomes: "name" | "age"
type PersonKeys = keyof Person;

let key: PersonKeys;

key = "name"; //  okay
key = "age";  //  okay
key = "email"; // Error: "email" is not a key of Person