# Hack your login
## Starting point
[https://www.hackthebox.eu/invite](https://www.hackthebox.eu/invite)

Let's open the Console:
```text
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
.           The first step of the challenge!                                      .
.                                                                                 .
.                      uuuuuuu                                                    .
.                  uu$$$$$$$$$$$uu                                                .
.               uu$$$$$$$$$$$$$$$$$uu                                             .
.              u$$$$$$$$$$$$$$$$$$$$$u                                            .
.             u$$$$$$$$$$$$$$$$$$$$$$$u                                           .
.            u$$$$$$$$$$$$$$$$$$$$$$$$$u                   K E E P  C A L M       .
.            u$$$$$$$$$$$$$$$$$$$$$$$$$u                                          .
.            u$$$$$$"   "$$$"   "$$$$$$u                        A N D             .
.            "$$$$"      u$u       $$$$"                                          .
.             $$$u       u$u       u$$$                        H A C K            .
.             $$$u      u$$$u      u$$$                                           .
.              "$$$$uu$$$   $$$uu$$$$"                         T H I S            .
.               "$$$$$$$"   "$$$$$$$"                                             .
.                 u$$$$$$$u$$$$$$$u                             B O X             .
.                  u$"$"$"$"$"$"$u                                                .
.       uuu        $$u$ $ $ $ $u$$       uuu                                      .
.      u$$$$        $$$$$u$u$u$$$       u$$$$                                     .
.       $$$$$uu      "$$$$$$$$$"     uu$$$$$$                                     .
.     u$$$$$$$$$$$uu    """""    uuuu$$$$$$$$$$                                   .
.     $$$$"""$$$$$$$$$$uuu   uu$$$$$$$$$"""$$$"                                   .
.      """      ""$$$$$$$$$$$uu ""$"""                                            .
.                uuuu ""$$$$$$$$$$uuu                                             .
.       u$$$uuu$$$$$$$$$uu ""$$$$$$$$$$$uuu$$$                                    .
.       $$$$$$$$$$""""           ""$$$$$$$$$$$"              HackTheBox           .
.        "$$$$$"                      ""$$$$""           info@hackthebox.eu       .
.          $$$"                         $$$$"                                     .
.                                                                                 .
.    This page loads an interesting javascript file. See if you can find it :)    .
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
```

It's came from this line:
```html
<script defer="" src="https://www.hackthebox.eu/js/calm.js"></script>
```

## Looking for the hint
Let's start to look for the JS file:
```html
<script defer="" src="/js/inviteapi.min.js"></script>
```

Content:
```javascript
//This javascript code looks strange...is it obfuscated???

eval(function(p,a,c,k,e,r){e=function(c){return c.toString(a)};if(!''.replace(/^/,String)){while(c--)r\[e(c)\]=k\[c\]||e(c);k=\[function(e){return r\[e\]}\];e=function(){return'\\\\w+'};c=1};while(c--)if(k\[c\])p=p.replace(new RegExp('\\\\b'+e(c)+'\\\\b','g'),k\[c\]);return p}('0 3(){$.4({5:"6",7:"8",9:\\'/b/c/d/e/f\\',g:0(a){1.2(a)},h:0(a){1.2(a)}})}',18,18,'function|console|log|makeInviteCode|ajax|type|POST|dataType|json|url||api|invite|how|to|generate|success|error'.split('|'),0,{}))
```

Tried to [Deobfuscate](http://deobfuscatejavascript.com/) but didn't work :(

This file add a function to the console:
```javascript
makeInviteCode()
```

Let's run it:
```javascript
makeInviteCode()

undefined

VM26:1

1.  {0: 200, success: 1, data: {…}, hint: "Data is encrypted … We should probably check the encryption type in order to decrypt it…"}

1.  0: 200
2.  data:

1.  data: "SW4gb3JkZXIgdG8gZ2VuZXJhdGUgdGhlIGludml0ZSBjb2RlLCBtYWtlIGEgUE9TVCByZXF1ZXN0IHRvIC9hcGkvaW52aXRlL2dlbmVyYXRl"
2.  enctype: "BASE64"
3.  \_\_proto\_\_: Object

4.  hint: "Data is encrypted … We should probably check the encryption type in order to decrypt it…"
5.  success: 1
6.  \_\_proto\_\_: Object
```

The result is a string `SW4gb3JkZXIgdG8gZ2VuZXJhdGUgdGhlIGludml0ZSBjb2RlLCBtYWtlIGEgUE9TVCByZXF1ZXN0IHRvIC9hcGkvaW52aXRlL2dlbmVyYXRl` encrypted in `BASE64`.

Let's decode [https://codebeautify.org/base64-decode](https://codebeautify.org/base64-decode).

Results: `In order to generate the invite code, make a POST request to /api/invite/generate`.

## Getting the key
Let's post with [https://reqbin.com/](https://reqbin.com/)
```text
URL: https://www.hackthebox.eu/api/invite/generate
Type: POST
```

Results:
```json
{
    "success": 1,
    "data": {
        "code": "UktHSEQtV0ZKRFAtRFFPUlAtUEpJU0ctWFVCS0g=",
        "format": "encoded"
    },
    "0": 200
}
```

Let's decode [https://codebeautify.org/base64-decode](https://codebeautify.org/base64-decode).

Results: `RKGHD-WFJDP-DQORP-PJISG-XUBKH`.

**I'm in :)**
