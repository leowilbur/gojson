# gojson

Gojson is a lightweight and fast JSON parser for Go. It is inspired by [gjson](https://github.com/tidwall/gjson), but adds a new `Set` method to make it easier to modify existing JSON documents.

## Installation

To install gojson, use `go get`:

```
go get github.com/leowilbur/gojson
```

## Usage

Gojson provides a simple API for parsing and manipulating JSON documents.

### Parsing

To parse a JSON document, use the `Parse` function:

```go
data := `{"name": "John Doe", "age": 42}`

json, err := gojson.Parse(data)
if err != nil {
    // handle error
}
```

### Accessing Values

Once you have parsed a JSON document, you can access its values using the `Get` method:

```go
name := json.Get("name").String() // "John Doe"
age := json.Get("age").Int() // 42
```

### Modifying Values

Gojson also provides a `Set` method for modifying existing values in a JSON document:

```go
gojson.Set("name", "Jane Doe")
gojson.Set("age", 43)
```

### Serializing

To serialize a JSON document, use the `String` method:

```go
data := json.String() // {"name": "Jane Doe", "age": 43}
```

## License

Gojson is released under the MIT license. See [LICENSE](LICENSE) for details.