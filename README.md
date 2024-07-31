# cURL request sending utility
## Minimal tool to allow using curl and jq like postman

`send_request` formulates and runs a curl request based on the a request.json file, where it will substitute any variable like `$var` with the appropriate environment variable.

Depends on `jq` and `curl`.

# Installation
Put `send_request` script somewhere in your path like `~/.local/bin`

# Common usage:
create request directory with a request.json file, and optionally a vars.sh and data.json file
```
send_request example_request
```

You can either give `send_request` a directory name (a request) to run, or run it in a request directory

# Setting Environment Variables
`send_request` will use environment variables to substitute into any field in
request.json or data.json. As an example, you could set an env var to the result
of another query:

```
export authstr=$(curl https://get-auth.com | jq -r '.authstr')
```
