# Part 4 - Strings and ES6 Template Strings

Welcome back, in the [previous](https://tech.io/playgrounds/6618/modern-es6-javascript-pt--3) article we covered the **Number** Datatype within JavaScript. Now we will cover **Strings** and also ECMAScript 6, **Template Strings**!

## Strings

In ECMAScript 5 and below, A string literal could only be wrapped in single quotes or double quotes. It can contain zero or more characters. The `\`(backslash) is the escape character. JavaScript was built at a time when Unicode was a 16-bit character set, so all characters in JavaScript are 16 bits wide. The escape sequences allow you to insert characters into strings that are not normally permitted, such as backslashes, quotes, and control characters. 

```javascript runnable
let a = "I am a double quoted string";
let b = 'I am a single quoted string'; // I like this more.

console.log(a); //=> I am a double quoted string
console.log(b); //=> I am a single quoted string
```   

**Concatenation**: Strings are immutable. Once you add them, they can never be changed. That said, it is very easy to make a new string by concatenating other strings together with the `+` operator.

```javascript runnable
let videos = 'Cat ' + 'Videos ' + 'on the web.';
console.log(videos); //=> Cat Videos on the web.
```

## Template Strings

Also known as Template literals, ECMAScript 6’s template literals provide syntax for creating domain-specific languages (DSLs) for working with content in a safer way than the solutions available in ECMAScript 5 (and below).

In Technical terms, To allow developers to solve more complex problems, this scheme extends the ECMAScript syntax with syntactic sugar to allow libraries to provide DSLs that easily produce, query, and manipulate content from other languages that are immune or resistant to injection attacks such as XSS, SQL Injection, etc.

That said, in reality, template literals are simply ECMAScript 6’s answer to the following features that JavaScript lacked in ECMAScript 5 and in earlier versions:

- **Multiline strings**: A formal concept of multiline strings
- **Basic string formatting**: The ability to substitute parts of the string for values contained in variables
- **HTML escaping**: The ability to transform a string so it is safe to insert into HTML

The working community of ES6 decided that instead of adding more functionality to JavaScript’s already existing strings, they will provide template literals that would represent an entirely new approach to solving these problems. In simple terms, template literals just act like those regular strings but delimited by backticks (`) instead of double or single quotes. For example, consider the following:

```javascript runnable
let message = `Hello world!`;

console.log(message);             //=> Hello world!
console.log(typeof message);      //=> string
console.log(message.length);      //=> 12
```    

As you can see, the above code shows how the variable message contains a normal JavaScript string. The template literal syntax is used to create the string value, which is then assigned to the message variable. If you want to use a backtick within a string, you can just escape it with a backslash (\), as like below:

```javascript runnable
let message2 = `\`Hello\` world!`;

console.log(message2);             // `Hello` world!
console.log(typeof message2);      // string
console.log(message2.length);      // 14
```    

Please remember that there’s no need to escape either double or single quote inside the template literals.

**Multiline Strings:** Since the first version of the language, JavaScript community has been wanting a way to create multiline strings. But unfortunately, when you’re using double or single quotes, strings must be completely contained on a single line.

That said, JavaScript does have a workaround for creating multiline strings. You can create multiline strings by using a backslash (\) before a newline. Here’s an example:

```javascript runnable
var message3 = "Multiline \
string";

console.log(message3);  
```   

As you see, this string has no newlines present when printed to the console because the backslash is treated as a continuation rather than a newline. If you want to show a newline within the output, you’d need to manually include it:

```javascript runnable
var message4 = "Multiline \n\
string";

console.log(message4);        
``` 

Other pre-ECMAScript 6 attempts to create multiline strings usually relied on arrays or string concatenation, such as the following:

```javascript runnable
var message5 = [
    "Multiline ",
    "string"
].join("\n");

var message6 = "Multiline \n" +
    "string";

console.log(message5);
console.log(message6);
```       

In pre-ECMAScript 6 era, creating multiline strings for arrays found to be very useful for **HTML escaping,** and/or proper indentation of your HTML within JavaScript. 
You would simply do something like:

```javascript runnable
var oldTemplate = [
  '<div class="callout">',
    '<p>Foo Bar Baz are awesome</p>',
  '</div>'
].join('');

console.log(oldTemplate);
```   

This may seem useful to you and make some sense but honestly, come ECMAScript 6, this sounds like you are just faking into the DOM. Clearly, not a great way! Here’s how you do them in ES6.

```javascript runnable
var newTemplate = `
  <div class="callout">
    <p>Foo Bar Baz are awesome</p>
  </div>
`;

console.log(newTemplate);
```     

**Making Substitutions:** To this point, template literals may just look like to you as fancier versions of normal JavaScript strings. But, the real difference between the two is in template literal substitutions. It allows you to embed any valid JavaScript expression inside a template literal and output the result as part of the string. Here’s how:

```javascript runnable
let friendsName = "Nicolas Coden"
let friendsMessage = `My friend ${friendsName} is a genius.`;

console.log(friendsMessage);
//=> My friend Nicolas Coden is a genius.
```

The substitution `${friendsName}` accesses the local variable name and inserts it into the `friendsMessage` string. The message variable would then holds the result for the substitution.

> A template literal can access any variable accessible in the scope in which it is defined. Attempting to use an undeclared variable in a template literal throws an error in strict and non-strict modes.

As all substitutions are just JavaScript expressions, you can substitute more than just simple variable names. You can easily embed calculations, function calls, and more.

## References

This story has been proudly referenced by these books below:

- [Eloquent JavaScript](https://www.amazon.com/Eloquent-JavaScript-Modern-Introduction-Programming/dp/1593272820)
- [JavaScript the Good Parts](https://www.amazon.in/JavaScript-Good-Parts-Crockford/dp/8184045220)
- [Understanding ECMAScript 6](https://www.amazon.com/Understanding-ECMAScript-Definitive-JavaScript-Developers/dp/1593277571)
## Thanks a lot…

***If you would like to hire me for your next cool project, or just want to say hello… my twitter handle is [@harmanmanchanda](http://bit.ly/tw-harry) for getting in touch with me! My DM’s are open to the public so just hit me up.***
