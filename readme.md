# NORTHSTAR Tutorial

This repo contains some tutorials are contextualizing the [NORTHSTAR](https://github.com/zangster300/northstar) example repo.

The tutorial will assume some familiarity with [Go][1] and [Datastar][2], but for the most part will build up concepts slowly.

## tl;dr

NORTHSTAR is a starter repo for jumpstarting a Datastar project with a Go backend. It contains implementations for some common and idiomatic Datastar patterns like using CQRS, event streaming and "Fat Morphs".

## Breakdown

The tutorial is broken up in to parts to help focus on a single topic at a time. Each part will build on the previous part.

1. TODOs - Most correct way to put things together with fat morph, and event bus and a long lived SSE connection pushing new state down as fragments.

1. Counter buttons - Shows handling local state vs global state.

1. Reverse example - Vanilla custom element integration.

1. Sortable - Integrating existing JS/TS libs and drive them with Datastar and how to use lit to build Web Components.

1. Tooling - Setting up additional tooling providing an awesome developer experience.

## Progress

1. TODOs - In Progress
1. Counter buttons - Not started
1. Reverse example - Not started
1. Sortable - Not started.

## Notes

Rocket and Stellar are right around the corner so this tutorial may or may not reflect the most up to date with regards to styling and working with Web Components. That said the info will still be relevant and shouldn't impact understanding core Datastar and NORTHSTAR concepts.

While the NORTHSTAR repo is fully featured with great defaults as far as tooling and dev experience go these tutorials will primarily focus on essential concepts and link out to the NORTHSTAR repo for more context or concrete examples.

[1]: https://go.dev/
[2]: https://data-star.dev/
