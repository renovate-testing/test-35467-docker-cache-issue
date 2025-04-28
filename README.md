# minimal-reproduction-template

First, read the [Renovate minimal reproduction instructions](https://github.com/renovatebot/renovate/blob/main/docs/development/minimal-reproductions.md).

Then replace the current `h1` with the Renovate Issue/Discussion number.

## Current behavior

Renovate does not connect to pkg.dev when using a host rule with authentication, but only when a secret is referenced in the hostRule. When using a string, it DOES contact pkg.dev (and fails authentication). This is when used with Kubernetes resources alone.

When a Dockerfile is used, then everything works. The pkg.dev registry is contacted and authentication is performed correctly using the stored secret.

When using both, the results seem to be inconsistent. I can't reproduce a consistent repo that works or fails. I had both manifests in this repo last week and it was working, but today (4/28/2025) it was failing after I updated the readme file. 

## Expected behavior

I expect the renovate app to connect to pkg.dev for images referenced in Kubernetes Manifests and to use the authentication I have provided in a secret without having to add a Dockerfile to this repo. 

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/35467
