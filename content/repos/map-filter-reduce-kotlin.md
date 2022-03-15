---
title: Map/Filter/Reduce Kotlin
icon: kotlin
icon_pack: custom
summary: 'How to Map/Filter/Reduce a List of Objects in Kotlin'
github_user: mstine
github_repo: atomic-repos/atomic-repos-map-filter-reduce-kotlin
author: Matt Stine
date: 2022-03-14
tags:
    - kotlin
---

Today we're going to look at how Kotin allows you to easily filter and aggregate a data set using
higher-order functions like `map`, `filter`, and `reduce`.

(_While Kotlin does have a `reduce` function, we'll go ahead and use Kotlin's `average` function since we're taking an average in this example._)

This example was inspired by Exercise 40 from _Exercises for Programmers: 57 Challenges to Develop Your Coding Skills._ by Brian P. Hogan.
In that exercise, you're provided with a dataset of employees.
We're going to whip up our own dataset inspired by the characters in everyone's favorite 90's cult
office-themed movie, _Office Space_.

We'll be implementing the following "queries" on our "database":

- Find all employees where their last name matches a search string.
- Find all employees with a specific job title.
- Find all employees that have been terminated since a specific date.
- Get the average service time (in days) for all employees.
- Get the average service time (in days) for all employees with a specific job title.

Higher-order functions are simply functions that can either accept other functions as arguments or return functions as values (or both!):

- `map` returns a new collection where each item is transformed by the function we provide.
- `filter` returns a new collection where each item is only retained if it matches the predicate function (a function that returns `true` or `false`) we provide.
- `reduce` returns a single value calculated by starting with the first item in the collection and applying the function we provide to each successive element, accumulating the "total" along the way. If we'd used `reduce` instead of `average`, we could have provided `Long::plus` and then divided the return value by `employees.count()`.

If you'd like to explore more of Kotlin's higher-order collection functions, take a look at [Common Operations](https://kotlinlang.org/docs/collection-operations.html#common-operations) in the Kotlin documentation.

---

## Code

{{% code file="/static/hello-world-kotlin/src/main/kotlin/dev/atomicrepos/kotlin/mfr/MapFilterReduce.kt" language="kotlin" %}}

## Tests

{{% code file="/static/hello-world-kotlin/src/test/kotlin/dev/atomicrepos/kotlin/mfr/MapFilterReduceTest.kt" language="kotlin" %}}
