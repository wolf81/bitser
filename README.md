# bitser

[![Build Status](https://travis-ci.org/gvx/bitser.svg?branch=master)](https://travis-ci.org/gvx/bitser)
[![Coverage Status](https://coveralls.io/repos/github/gvx/bitser/badge.svg?branch=master)](https://coveralls.io/github/gvx/bitser?branch=master)

Serializes and deserializes Lua values with LuaJIT.

    local bitser = require 'bitser'

    bitser.register('someResource', someResource)
    bitser.registerClass(SomeClass)

    serializedString = bitser.dumps(someValue)
    someValue = bitser.loads(serializedString)
    serializedData = love.filesystem.newFileData("filename")
    someValue = bitser.loadData(serializedData:getPointer(), serializedData:getSize())

Pull requests, bug reports and other feedback welcome! :heart:

Bitser is released under the ISC license (functionally equivalent to the BSD
2-Clause and MIT licenses).

## Why would I use this?

Because it's fast. Because it produces tiny output. Because the name means "snappier"
or "unfriendlier" in Dutch. Because it's safe to use with untrusted data.

Because it's inspired by [binser](https://github.com/bakpakin/binser), which is great.

## How do I use the benchmark thingy?

Download zero or more of [binser.lua](https://github.com/bakpakin/binser/master/binser.lua),
[ser.lua](https://github.com.com/gvx/Ser/master/ser.lua),
[smallfolk.lua](https://github.com/gvx/Smallfolk/raw/master/smallfolk.lua),
[serpent.lua](https://github.com/pkulchenko/serpent/raw/master/src/serpent.lua) and
[MessagePack.lua](https://github.com/fperrad/lua-MessagePack/raw/master/src/MessagePack.lua), and run:

    love .

You do need [LÖVE](https://love2d.org/) for that.

You can add more cases in the folder `cases/` (check out `_new.lua`), and add other
serializers to the benchmark in `main.lua`. If you do either of those things, please
send me a pull request!

## You can register classes?

Yes. At the moment, bitser supports MiddleClass, SECL, hump.class and Slither (and
probably some other class libraries by accident).
