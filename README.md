# Recogni coding standard

This project contains various coding standard related assets sorted by programing language.


## Python

Currently we use the following linter settings with the [`flake8 linter`](http://flake8.pycqa.org/en/latest/):
```
flake8 --ignore=E221,E241,E251 *.py
```

The above settings disable whitespace alignment related warnings in python (I like nicely lined up vars).

These leave us with fairly aggressive settings - all other options that we find irritating can be `ignore`d as needed.

### Testing

Python's built-in [`unittest`](https://docs.python.org/2/library/unittest.html) library is currently employed in a few of our projects.


## Golang

All `.go` code should conform to [`gofmt`](https://golang.org/cmd/gofmt/).  Most editors (sublime, atom, vi, emacs) have modes / scripts which will auto-run gofmt on-save (etc).

Due to some of go's private/public semantics being tied to naming, all production go code will conform to the broad outlines set forth in the [effective go article](https://golang.org/doc/effective_go.html).

Other code cleanup or coverage tools are TBD.

Possibly interesting to look into [`golint`](https://github.com/golang/lint), which has been a little too aggressive and suggestive in the past.

### Vendoring

For now, the chosen packaging method for changing upstream dependencies will be to use `govendor` to manage each project's `vendor` directory.

TODO: Evaluate go modules

### Documentation

Using things like `golint` will suggest documentation tips which fit right into [`godoc`](https://blog.golang.org/godoc-documenting-go-code). Other than adding auto-generated-demonstrative HTTP documentation, we will probably stick with the above.

### Testing

All tests will be run using `go test ...`.

TODO: Coverage, etc


## C / C++

We do not have an explicit standard here (yet).  UE4 has infinitely long lines (/s) while other low-level C is neatly contained within 80 cols.

For future Recogni projects requiring a coding standard, [the google cpp style guide](https://google.github.io/styleguide/cppguide.html) is probably a good place to start.

### Testing

[Google test](https://github.com/google/googletest) has been easy to customize and scale with large C++ projects in the past.
