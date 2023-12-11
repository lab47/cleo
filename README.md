# cleo

Simple Golang commandline creation utility

## Usage

Cleo infers specially defined functions to create command line
flag parsing.

```go
func login(ctx context.Context, opts struct {
	Email    string `short:"e" long:"email" description:"email address for account"`
	Password string `short:"p" long:"password" description:"password for account"`
}) error {
	...
}

cmds := map[string]cli.CommandFactory{
    "login": cleo.Infer("login", "log into the service", login),
}

```
