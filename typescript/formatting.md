## TypeScript : Code indentation
The regular indentation for a typescript project is 2 for an horizontal tab. This is quite good for small file. 
However with large file, this make the script unreadable. Here is an example.

**Bad Indentation**
```ts
const somevar   = 'pop';

switch( somevar ) {
  case 'pop':
    new FooClass();
  break;
}
```

**Good Indentation**
```ts
const somevar   =   'pop';

switch( somevar ) {
    case 'pop':
        new FooClass();
    break;
}
```

## TypeScript : Code Formatting

Since TypeScript is a superset of Javascript, the same formatting rules applyied to it. 
This start with the way the variable are declared.

### Using camelCase while naming variables :

```ts
const my_variable = 'some variable';
const Anothervariable = 'the value';
```

```ts
const myVariable = 'some variable';
const anotherVariable = 'the value';
```

### Align same sharacters/sign when they're grouped

An example of what to avoid
```ts
const variable = 10;
let username = 'John Doe';
const anotherVariable     = 20;
```
An example of what is recommended
```ts
const variable          = 10
const anotherVariable   = 20;
let username            = 'John Doe';
```

if `const` and `let` is used to define a variable, they should be grouped as well.

## TypeScript : How space is used
Using the space is good to make the code more cleaner and easy to read. Here is how we're using the space.

### On conditional statement
```ts
if(true){
}
```

Good Example
```ts
if ( true ) {
}
```
This apply even if the condion has more than one entity, or is an array.

```ts
if ( users[0].name === 'johndoe' ) {
    // the script goes here =>
}
```

### On array and object

Bad Example
```ts
const users = ['john', 'doe'];
console.log(users[ 0 ]);

const names = {
  'first_name': 'John Doe'
}
console.log(name['first_name']);
// or
console.log(name.first_name);
```

Good Example
```ts
const users = [ 'John', 'Doe' ];
console.log( users[0] );

const names = {
    'firstName'  : 'John Doe'
}
console.log( names[ 'firstName' ] );
// or
console.log( names.firstName );
```

## TypeScript : the art of commenting the code
If we're supposed to work as a team, we need to provide all the informations about how we code, so that the collegue can understand how you've coded and why you did that that way. However, overusing comments is not recommended as well.

### While Defining Variables
Using a comment while defining a single variable is not required. However, while defining a set of variables, this might be useful
to understand the purpose of the variables.

```ts
/** 
 * Defining Variable for 
 * Script Validation
**/
const licence   =   '0819209309U';
const userName  =   'John Doe';
```

### While Defining the functions
Using a comment to describe a function is required. This shoudl desccribe de function, the parameters and what is the returned value.

```ts
/**
 * Display the real username
 * @param object user object
 * @return string the real username
**/
function getRealUserName( user: User ): string {
    return user.name;
}
```
Providing a type of variable is also required. For this previous example, the function require an object of type "User" and return a string. The sale rule apply while defining a class.
