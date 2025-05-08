1: Explain the difference between any, unknown, and never types in TypeScript.

Any: This type justifies it's name. Any type can include anything, this can be a number, string or boolean. This is a flexible type and we can use this when we don't care about the type of the thing.

let x: any = "Hello world";
x = 42;
x = true;

We can assign anything in "x" here, it won't give ant error.

Unknown: This is similar to Any type but not exactly. This is like we don't know the type of the item but not anything can be it's type. We can't do operations of unknown type.

let x : unknown = 200;

console.log(x+1)

This will give an error. But

let x: unknown = "Hello world";
let y: unknown = 200;
let z: unknown = true;

These won't give any error

Never: We use type Never when we know that the type of the function will never going return anything. We mostly use this for handling error messages.

const throwError = (msg: string): never => {
throw new Error(msg);
};

throwError("Error message");

2: Provide an example of using union and intersection types in TypeScript.

Union: We use symbol (|) pipe to define Union. It works as (Or). To select among things we use union. This works in conditional values, like if any of the given value matches this going to deliver us the result.

Example:

type MyAnswer = {
goingOut: boolean;
wantToEat: boolean;
};

type MyMood = {
isHappy: boolean;
};

type Mood = MyAnswer | MyMood;

here, in Mood type if we include items from MyAnswer or MyMood it will work. But we must include at least all the items from any one of the types (MyAnswer or MyMood).

Intersection: This is opposite of Union. This works as AND or Plus. Intersection works only if all the condition we provided are true. Using intersection we include all the items from types.

type MyAnswer = {
goingOut: boolean;
wantToEat: boolean;
};

type MyMood = {
isHappy: boolean;
};

type MyFeeling = MyAnswer & MyMood;

here, in MYFeeling type we must include all the items from MyAnswer and MyMood. We can't miss any of the item. Let's say if we include "goingOut" and "wantToEat" but not "isHappy", it will give us error.
