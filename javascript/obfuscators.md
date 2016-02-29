# JavaScript security with obfuscators.

Anyone visiting your site has access to your client-side JavaScript code. It means that if hackers want to tamper with your code, they can.

However, there is a way to make it harder for hackers to find attack vectors. This is <strong>not</strong> properly securing your JS code, it just makes it harder to read. This is called obfuscation.

Obfuscation is the process of going through your code, transforming and rearranging it all with the goal of making it impossible to read and understand, but keeping its functionality.

Example of unprotected code:

```
(function() {
    function add1(element, index, array) {
        array[index]=element+1;
    }
    function apply(functions, integers) {
        if(!Array.isArray(functions)) {
             integers.forEach(functions);
        }
    }
})
```

Same code with obfuscation:

```
var _0xd611=["\x69\x73\x41\x72\x72\x61\x79","\x66\x6F\x72\x45\x61\x63\x68"];(function(){function _0xa547x1(_0xa547x2,_0xa547x3,_0xa547x4){_0xa547x4[_0xa547x3]=_0xa547x2+1}function _0xa547x5(_0xa547x6,_0xa547x7){if(!Array[_0xd611[0]](_0xa547x6)){_0xa547x7[_0xd611[1]](_0xa547x6)}}})
```
