# TODO

Let's build a simple TODO application to demonstrate how [Command Query Responsibility Segregation][1], pushing updates over [SSE][2] and updating the dom using "Fat Morph" (morphing large sections of the DOM) can greatly simplify implementing a real time experience.

## Setup

Start by setting up a new Go project.

```bash
mkdir northstart-tutrial && cd northstar-tutorial
go mod init northstar-tutorial
```

This creates a go.mod file that will track your project's dependencies as we work through this project.

## Create basic HTTP server

Create a `main.go` file with a minimal HTTP server.

```go
package main

import (
    "log"
    "net/http"
)

func main() {
    log.Println("Server running on http:localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
       log.Fatal(err)
    }
}
```

Now run the server:

```bash
go run main.go
```

You'll see some output about the server running on port 8080. When accessing it you'll get a 404 because we haven't added any routes yet!

## Add HTTP router

Let's add our first route. Update the `main.go` file.

```go
package main

import (
    "log"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        w.Header().Set("Content-Type", "text/html")
        w.Write([]byte("<h1>NORTHSTAR App</h1>"))
    })

    log.Println("Server running on http:localhost:8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        log.Fatal(err)
    }
}
```

We now have our first route that serves up a basic "NORTHSTAR App" header! We know we'll be adding more routes so we'll go ahead and add the [chi][3] module to help keep things tidy.

```shell
go get github.com/go-chi/chi/v5
```

And again update our `main.go` file.

```go
package main

import (
    "log"
    "net/http"

    "github.com/go-chi/chi/v5"
)

func main() {
    r := chi.NewRouter()

    r.Get("/", func(w http.ResponseWriter, r *http.Request) {
        w.Header().Set("Content-Type", "text/html")
        w.Write([]byte("<h1>NORTHSTAR App</h1>"))
    })

    log.Println("Server running on http:localhost:8080")
    if err := http.ListenAndServe(":8080", r); err != nil {
        log.Fatal(err)
    }
}
```

Give `go run main.go` another run and make sure you're seeing the same "NORTHSTAR Tutorial" output.

## Add initial /todos route

NOTE: Simple GET route that returns basic HTML (no D\* yet)

## Implement TODO display from memory

NOTE: In-memory slice/map, render as HTML

## Introduce Templ

NOTE: Refactor HTML string to use Templ

## Add TODO creation

NOTE: POST endpoint that appends to in-memory store

## Introduce Datastar

NOTE: Add SSE ednpoint and Datastar attrs to make it reactive

## Add TODO deletion

NOTE: DELETE endpoint completing in-memory CRUD

## Introduce embedded NATS

NOTE: Showcase persistent event streaming for real-time updates

## Refactor CQRS

NOTE: Commands publish to NATS, queries subscribe to events

## Far Morphs

NOTE: show fragment-based updates of page

[1]: https://www.geeksforgeeks.org/system-design/cqrs-command-query-responsibility-segregation/
[2]: https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events
[3]: https://github.com/go-chi/chi
