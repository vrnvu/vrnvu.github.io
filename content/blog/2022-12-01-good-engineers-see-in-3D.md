
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

![2d vs 3d](https://t4.ftcdn.net/jpg/05/12/86/27/360_F_512862789_abYbb2RPLzpN8aAjteTBb4xGnRgqVSyw.jpg)

Gabo is a software engineer, and his team is responsible for a product that enables users to create and manage a TODO list. This product has three primary components:

- **Public API**: includes simple HTTP operations such as listing my TODOs, creating a TODO, and completing a TODO.
- **Core service**: processes HTTP requests.
- **Database**: a persistence layer for storing and managing the state of a user's TODO list.

Let's assume this product runs on AWS. The team uses ALB, runs instances of the service in t3.medium EC2 instances, and uses DynamoDB as the database.

As the traffic grows, the team needs to adapt the product to meet the new requirements. There are two scaling alternatives:

- **Horizontal scaling**: adding more t3.medium instances.
- **Vertical scaling**: changing the instance type to a t3.large with more resources.

One way to make the decision is to analyze the cost. The team knows the cost of one instance and how much traffic it can handle. With this information, they can consider both alternatives and choose the most efficient one.

Stop. Did you see the problem? If you haven't yet, then you might be a 2D engineer. Good engineers can see in 3D.