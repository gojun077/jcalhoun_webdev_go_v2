Notes on hello_world
=======================

Now golang uses modules instead of GOPATH for handling dependencies,
so you will have to run `go mod init ..` with appropriate args
so that the golang compiler will be able to find module *main*.
Otherwise you will get the following error when trying to run your
build command:

```sh
env GOOS=linux GOARCH=amd64 go build -v -o bin/$(basename $(pwd)) && go test -v && go vet
go: cannot find main module
```

Since I will not be using symantic versioning, I do not want to init
a v2 module; I will just init a v0/v1 module with the following in
this current directory:

```sh
go mod init main/m
```
Now you should be able to compile `main.go` into a binary. Note that
the binary will be built in `hello_world/bin` and will be named
by default the name of the project folder 'hello_world'.
