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

```ts

```

```ts
const myVariable = 'some variable';
const anotherVariable = 'the value';
```
