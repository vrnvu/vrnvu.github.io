+++
title = "you use git wrong"
date = 2023-01-31
draft = false
 

[taxonomies]
categories = ["programming"]
tags = ["programming"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---

# you use git wrong

## fetching changes from a PR

Imagine you are working on a project and want to fetch some changes that you see in a PR. For example let's take [this](https://github.com/kubernetes/kubernetes/pull/115382) one.

If you are working on your local first you will need to add the remote.

> git remote add liggitt https://github.com/liggitt/kubernetes/tree/typecheck-stdlib

Then fetch it.

> git fetch liggitt

And then checkout to the branch you want to check.

> git checkout liggitt/typecheck-stdlib

And at this point you will be at the patch you wanted to check. Take some extra steps if you want to take this patch and apply it another branch.

## fetching changes using the patch

We are still going to use the same PR as example. The url is: [https://github.com/kubernetes/kubernetes/pull/115382](https://github.com/kubernetes/kubernetes/pull/115382)

Now from this URL let's get the patch of changes directly. Which we can do by adding `.patch` at the end of the url.

[https://github.com/kubernetes/kubernetes/pull/115382.patch](https://github.com/kubernetes/kubernetes/pull/115382.patch)

Now we can simply curl it and apply it to our project.

> curl -L https://github.com/kubernetes/kubernetes/pull/115382.patch | git am

And we are done. We can apply the patch directly to our work in progress and play with it.