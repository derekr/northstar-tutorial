# TODO

Let's build a simple TODO application to demonstrate how [Command Query Responsibility Segregation][1], pushing updates over [SSE][2] and updating the dom using "Fat Morph" (morphing large sections of the DOM) can greatly simplify implementing a real time experience.

## Setup

Start by setting up a new Go project.

```go
go mod init northstar-tutorial
```

This creates a go.mod file that will track your project's dependencies as we work through this project.

## Create basic HTTP server

NOTE: Minimal server listening on port

## Add HTTP router

NOTE: Add chi

## Add initial route

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
