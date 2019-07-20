#### How can I use ES6 today?

Most of ES6 is already supported in current engines, consult <a href="http://kangax.github.io/compat-table/es6/" target="_blank">Kangax’ ES6 compatibility table </a>to find out what is supported where.

#### Isn’t ECMAScript 6 now called ECMAScript 2015?

Yes and no. The official name is ECMAScript 2015, but ES6 is the name that everyone knows and uses.
After ES6, ECMAScript editions are created via a new process and a yearly release cycle. That seems like a good opportunity to switch to the new naming scheme. Therefore, I’ll use the name “ECMAScript 2016” for the edition after ES6.

#### Does it still make sense to learn ECMAScript 5?

ES6 is increasingly well supported everywhere. Does that mean that you shouldn’t learn ECMAScript 5, anymore? It doesn’t, for several reasons:

- ECMAScript 6 is a superset of ECMAScript 5 – new JavaScript versions must never break existing code. Thus, nothing you learn about ECMAScript 5 is learned in vain.
- There are several ECMAScript 6 features that kind of replace ECMAScript 5 features, but still use them as their foundations. It is important to understand those foundations. Two examples: classes are internally translated to constructors and methods are still functions (as they have always been).
- As long as ECMAScript 6 is compiled to ECMAScript 5, it is useful to understand the output of the compilation process. And you’ll have to compile to ES5 for a while (probably years), until you can rely on ES6 being available in all relevant browsers.
- It’s important to be able to understand legacy code.

#### Isn’t the ES6 specification very big?

The ECMAScript specification has indeed grown tremendously: The ECMAScript 5.1 PDF had 245 pages, the ES6 PDF has 593 pages. But, for comparison, the Java 8 language specification has 724 pages (excluding an index). Furthermore, the ES6 specification contains details that many other language specifications omit as implementation-defined. It also specifies how its standard library works.
