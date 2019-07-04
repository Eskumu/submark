# submark
Subset of Markdown

## Features

* Convert headings 
    * `# heading`  -> `<h1> heading </h1>`
    * `## heading`  -> `<h2> heading </h2>`
    * `### heading`  -> `<h3> heading </h3>`
    * `#### heading`  -> `<h4> heading </h4>`
    * `##### heading`  -> `<h5> heading </h5>`

* Convert strong
    * `**strong**` -> `<strong>strong</strong>`
    * `__strong__`-> `<strong>strong</strong>`


* Convert em
    * `**something**` -> `<em>something</em>`
    * `__something__`-> `<em>something</em>`


## Usage

Use it like this:
~~~
$ python3 submark.py something.md > something.html
~~~

or:
~~~
$ cat something.html | python3 submark.py > something.html
~~~

or:
~~~
$ echo '**hi**' | python3 submark.py
<strong>hi</strong>
~~~


## Testing

Test in a virtual environment with the usual incantations.

~~~
$ git clone https://github.com/okken/submark.git
$ cd submark
$ python3 -m venv venv --prompt submark
$ source venv/bin/activate
(submark) $ pip install -U pip
~~~

Then install `pytest` and `pytest-cov`.

~~~
(submark) $ pip install pytest pytest-cov
~~~

There's already a `.coveragerc` file to exclude `venv` or `.venv`.

Now run tests.

~~~
(submark) $ pip install pytest pytest-cov
(submark) $ pytest --cov=.
~~~

## Building a wheel

Make sure everything is committed before running `flit`.

~~~
(submark) $ pip install flit
(submark) $ flit build
~~~

Yep. That's it. 
There should be a wheel now sitting in a `dist` folder.

~~~
(submark) $ ls dist
submark-0.2-py2.py3-none-any.whl
submark-0.2.tar.gz
~~~

## Deploying

Flit does that too.

~~~
(submark) $ flit publish
~~~

But don't do that unless:

* You are Brian Okken

or:

* You are pointing to something other than pypi
* see https://flit.readthedocs.io/en/latest/upload.html



## History

* 0.1 Initial script and tests
* 0.2 build wheel with flit

