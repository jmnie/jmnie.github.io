---
title: Parallel Computing Notes
date: "2022-04-20"
tags: [tech, EN]
description: "This blog is a transcript about basic intro to Parallel Computing"
---

This blog is about some basic concepts of parallel computing. It includes the concept and comparison between serial computing and parallel computing. 

# Serial Computing 

![Serial Computing](./images/serial_computing.png)

- A problem is broken into a discrete series of instructions
- Instructions are executed sequentially one after another
- Only one instruction may execute at any moment of time

# Parallel Computing

![Parallel Computing](./images/parallel_computing.png)

- Be divided into sub-problem which can be solved simultaneously
- Execute multiple program instructions at any moment in time
- High e ciency with multiple computation resources than single computation resource

# Parallelism vs. Concurrency

## Concurrency

![Concurrency](./images/concurrency.png)

- Concurrency, application making progress on more than one task.
- Concurrency means executing multiple tasks at the same time but not necessarily simultaneously.

## Parallelism

![Parallelism](./images/parallelism.png)

- Parallelism means that an application splits its tasks up into smaller subtasks which can be processed in parallel, for instance on multiple CPUs at the exact same time (simultaneously).

## Matrix Multiplication Using Parallel Methods

### Matrix Computation 

![Matrix Computation](./images/matrix_computation.jpeg)

Sequential Algorithm
- Using nested loops in Code, time Complexity *O(N3)*

### Parallel Methods

Parallel Algorithm

![Parallel Methods](./images/matrix_compute_parallel.png)

- Divided Matrix A and B into small blocks
- Using parallel loops in Code, time Complexity O(M*N2)

## Neural Network: Initialize, Compute and Update Parameters

![Neural Network](./images/neural_network.png)

- Output = Input * HiddenParameters
- Number of parameters is pretty huge

## Map-Reduce: Large-Scale Matrix Multiplication

![Map Reduce](./images/map_reduce.png)

- Parallel and distributed algorithm processing big data sets.
- Proposed by Google, implemented in Hadoop and Spark.

# Application Scenraio 

![Applications](./images/app.png)

Scenarios that require processing large amounts of data in sophisticated
way.
- "Big Data", databases and data mining
- Artificial Intelligence
- Pharmaceutical design
- Financial and economic modeling

## GPU and Parallel Computing

![GPU Framework](./images/gpu.png)

- GPUs are designed to handle parallel processing more e ciently.

## CUDA - Compute Uni ed Device Architecture

- A parallel computing platform and programming model that enables dramatic increases in computing performance by harnessing the power of the graphics processing unit (GPU).
- Developed and released by NVIDIA in 2006
- Can run on all of NVIDIA's latest discrete GPUs
- Extension of the C, C++, and Fortran languages
- Operating Systems that Support it: Windows XP and later, Linux, and Mac OS X