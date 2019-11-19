# ADR-0002-python_api

* Status: Proposed
* Date: 2019-11-15

## Context 

The WhiteGlove is a new service that needs to developed in a REST and AWS Lambda friendly architecture.

## Considered Options

1. Python
2. JVM (Java or Scala)

## Decision Outcome

We will develop the REST API in python for the following reasons:

1. Compatible with AWS Lambda
2. API is small -- project complexity is small
3. Existing CRE scripts are written in python making for easier conversion

