# LUAloader
A class to parse an array saved with LUA into an PHP array

This file has been taken from the wowpl project (https://code.google.com/archive/p/wowlp/) and been posted to GitHub
 because i couldn't find it anywhere else and it is a useful addition to my toolbox (i don't have no need for the whole
 wowlp project)

**USAGE**

<pre>
include_once 'LUA_Parser.php';

$luafile = 'filename';

$p = new LUA_Parser($luafile);

$result = $p->toArray();

var_dump($result);
</pre>

Thats basically it.

Be aware that the parser does NOT handle files where the opening bracket is in the next line, it HAS to be in the same
line as the equal sign:

**works**:
<pre>
"varname" = {
  ["Default"] = "stuff"
} 
</pre>

**does NOT work**:
<pre>
"varname" = 
  {
    ["Default"] = "stuff"
  }
</pre>
