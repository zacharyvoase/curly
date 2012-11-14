# curly

Use the [curl][] command line from Python with minimal fuss.

  [curl]: http://curl.haxx.se

    >>> import curly
    >>> response = curly.curl('http://news.ycombinator.com/')
    >>> response.status
    200
    >>> response.msg.type
    'text/html'
    >>> response.read(6)
    '<html>'

A bit more complex (form POST with authentication):

    >>> res = curly.curl('https://api.stripe.com/v1/charges',
    ...     '-u', 'vtUQeOtUnYr7PGCLQ96Ul4zqpDUO4sOE:',
    ...     '-d', 'amount=400',
    ...     '-d', 'currency=usd',
    ...     '-d', 'description=Charge for test@example.com',
    ...     '-d', 'card[number]=4242424242424242',
    ...     '-d', 'card[exp_month]=12',
    ...     '-d', 'card[exp_year]=2012',
    ...     '-d', 'card[cvc]=123')

Streaming multipart file upload:

    >>> res = curly.curl('https://api.example.com/v1/savefile',
    ...     '-u', 'username:password',
    ...     '-F', 'bucket=foobar',
    ...     '-F', 'file=@/path/to/some/file')


## Installation

    pip install curly


## Unlicense

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any means.

In jurisdictions that recognize copyright laws, the author or authors of
this software dedicate any and all copyright interest in the software to
the public domain. We make this dedication for the benefit of the public
at large and to the detriment of our heirs and successors. We intend this
dedication to be an overt act of relinquishment in perpetuity of all
present and future rights to this software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>.
