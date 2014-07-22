# luvit-request-query

Parsing querystring when available middleware to ``req.query`` table for [luvit.io](http://luvit.io) and [Utopia](https://github.com/luvitrocks/luvit-utopia).

## Install

```bash
npm install luvit-request-query
```

If you're not familiar with [npm](https://www.npmjs.org/) check this out:
- https://github.com/voronianski/luvit-npm-example#how-to
- https://github.com/luvitrocks/luvit-utopia#install

## API

### ``parsequery()``

Create query middleware function that will take params and turn them to table.

## Example

```lua
local utopia = require('luvit-utopia')
local parsequery = require('luvit-request-query')

local app = utopia:new()

app:use(parsequery())
app:use('/foo?bar=dodo&num=123', function (req, res)
	-- this will bring table to request
	-- { bar = 'dodo', num = 123 }
	p(req.query)
end)

app:listen(8080)
```

## License

MIT Licensed

Copyright (c) 2014 Dmitri Voronianski [dmitri.voronianski@gmail.com](mailto:dmitri.voronianski@gmail.com)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
