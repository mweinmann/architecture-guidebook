# ADR-0001: AWS Lambda REST API

* Status: Proposed
* Date: 2019-11-14

## Context

The WhiteGlove is a new of APIs that ultimately updates the related domains maintained by the Infrastructure application.

## Considered Options

1. Develop and deploy a new micro-service with new APIs.
2. Extend Infrastructure with new WhiteGlove APIs.
3. AWS Lambda REST API

## Decision Outcome

We will develop AWS Lambda REST API that exposes the WhiteGlove APIs for the following reasons:

1. New team will be developing the WhiteGlove APIs.
2. The WhiteGlove API is used by a subset of the Infrastructure application users.
3. Low volume of requests per day. 
4. The WhiteGlove API might be deprecated as logic is migrated into the Attribution service.
5. Reduced Operations overhead.
