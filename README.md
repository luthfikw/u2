# u2
double underscore binding

## install

```bash
$ go get -u github.com/luthfikw/u2
```

```go
import "github.com/luthfikw/u2"
```

## usage

### ScanPrefix
get all u2 binding with a prefix

`ScanPrefix(q string, prefixs []string) (items map[string][]string)`


example:
```go
q := `
    hi __@name__, how are you today
    i am __:me__, nice to meet you
`

items := u2.ScanPrefix(q, []string{"@", ":"})
fmt.Printf("%+v\n", items)

// output
```

### ScanTags

get all u2tag binding

`ScanTags(q string, tag string) (nq string, tags []TagInfo, err error)`

example:

```go
q := `
    <foo[bar]{
        meta1: value;
        meta2: "value 2";
    }>
        hello world!
    </foo[bar]>
`

newq, items, err := u2.ScanPrefix(q, []string{"@", ":"})
if err != nil {
    panic(err)
}

fmt.Printf("%s\n\n%+v\n", newq, items)

// output
```

## contributing

we are open become contributor!
