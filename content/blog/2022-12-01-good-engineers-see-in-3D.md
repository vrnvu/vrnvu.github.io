
+++
title = "good engineers see in 3D"
date = 2022-12-01
draft = false

[taxonomies]
categories = ["culture"]
tags = ["culture"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---

# Good engineers see in 3D

Gabo is a software engineer. Gabo's team is responsible for a product that allows a user to create a TODO list and add/complete items. This product has 3 main components:

- Public API, with simple HTTP operations like list my TODOs, create a TODO, complete a TODO.
- A core service, that processes the HTTP request.
- Database, a persistence layer to store and manage the state of a user TODO list.

Let's imagine this product runs in AWS. It's not relevant. The team uses ALB, runs instances of the service in `t3.medium` ec2 instance and finally uses DynamoDB as database.

After some time, the traffic grows and we need to adapt our product to handle the new requirements. Here we have two scaling alternatives:

- **Horizontal**: we can add more `t3.medium` instances.
- **Vertical**: we can change the instance type to a `t3.large` which has more resources.

A way to proceed with the decision is to analyse the cost. We know how much one instance costs. We know how much traffic it can handle. With this data we can consider both alternative and choose the most efficient. 

Stop. Did you see the problem? If you haven't seen it yet, then you are a 2D engineer. Good engineers see in 3D.