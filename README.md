# MongoDB Aggregation Pipeline Bug: Incorrect $inc Operator Usage

This repository demonstrates a common error when using the `$inc` operator within MongoDB's aggregation pipeline. The `$inc` operator is intended for incrementing fields, but it's misused in this example, leading to unexpected results.

## Bug Description

The provided code attempts to increment the `count` field after it's been calculated in a `$group` stage. However, the `$inc` operator in its current position is applied after the `$group` stage, which is not valid.  The `count` field should be incremented *within* the `$group` stage.

## Solution

The solution involves correctly integrating the increment operation into the `$group` stage.  This ensures the increment operation works as expected.

## How to Reproduce

1. Clone the repository.
2. Set up a MongoDB instance.
3. Execute the `bug.js` script to observe the error.
4. Execute the `bugSolution.js` script to see the correct implementation.
