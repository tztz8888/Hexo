---
title: Game Physics Engine Development, Introduction Part
date: 2024-07-08 17:07:31
tags: 
  - Physics
  - GameDev
categories: ReadNotes
---

# 1. Introduction

## 1. 2 What's a Physics Engine, advantages and disadvantages

* classical mechanics, that is, the laws that govern how large objects move under the influence of gravity and other forces.
* The physics engine is basically a big calculator: it does the mathematics needed to simulate physics. But it doesn’t know what needs to be simulated.
* There are two compelling advantages for using a physics engine in your games.
  * time savings. Reuse code in another project is easy
  * quality. Physics engines makes sure all simulated objects behave credibly under most circumstances in complex physics world.

* Disadvantages
  * General purpose meaning no assumptions about the kinds of objects, resulting in potential waste of processing power.
  * Feed the engine with physics properties data can be too complex sometime.
  * scope. Developing a complete physics solution is too much effort for a small group.

## 1.3 Approaches to Physics Engine

* Creating a usable engine means balancing the **complexity of the programming task** with **the sophistication of the effects** you need to simulate.

* Types of Objects
  * full rigid bodies or so-called “mass aggregate” 
  * we can extend a mass aggregate engine into a full rigid-body system, simply by adding rotations. 
* Contact Resolution
  * how touching objects are processed
  * handle these contacts one by one, the “iterative” approach
    * It has the downside that one contact can affect another, and sometimes these interactions can be significant.
    * used in this book
  * calculate the exact interaction between different contacts and calculate an overall set of effects to apply to all objects at the same time. This is called a “Jacobian-based” approach.
    * Most physics middleware packages and several open-source physics engines use this approach
  * calculate a set of equations based on the contacts and constraints between objects.
    * This is called a “reduced coordinate” approach.
    * Very slow, not suitable for game.
* Impulses and Forces
  * “force-based” physics engine
    * impulses are simply forces acting over a very small space of time.
    * the mathematics of forces are more difficult than the mathematics of impulses.
    * Engines that are force-based tend to employ a Jacobian or reduced coordinate approach.
  * “impulse-based” physics engine
    * approach we will use in this book
    * easy to implement, very flexible and adaptable.
* Building in this book
  * rigid-body, iterative, impulse-based physics engine that I call Cyclone

## 1.4 The Mathematics of Physics Engines

* 3D mathematics
* quaternions, matrices

## 1.5 Source Code

* C++, object oriented
* Glut toolkit for rendering

## 1.6 How the book is Structured

* Particle Physics
* Mass Aggregate Physics
* Rigid-Body Physics
* Collision Detection
* Contact Physics
* Horizons