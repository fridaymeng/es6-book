On the web, you could tag ECMAScript 6 code via a dedicated Internet media type. Such a media type can be associated with a file via an HTTP header:

```html
Content-Type: application/ecmascript;version=6
```

It can also be associated via the type attribute of the &lt;script&gt; element (whose default value is text/javascript):

```html
<script type="application/ecmascript;version=6">
  ···
</script>
```

#### Implicit strict mode

The bodies of modules and classes are implicitly in strict mode in ECMAScript 6 – there is no need for the 'use strict' marker. Given that virtually all of our code will live in modules in the future, ECMAScript 6 effectively upgrades the whole language to strict mode.

The bodies of other constructs (such as arrow functions and generator functions) could have been made implicitly strict, too. But considering how small these constructs usually are, using them in sloppy mode would have resulted in code that is fragmented between the two modes. Classes and especially modules are large enough to make fragmentation less of an issue.
