---
layout: project
title: "Product Configuration"
modified:
excerpt: "System for configuration of arbitrary products consisting of a diversity of interchangable parts."
date: 2014-12-15
tags: [projects]
image:
  feature: configurator.png
---

<div markdown="0"><a href="http://jiekebo.info/conf" class="btn">Go to Project Site ></a></div>

The product configurator is used as aid in visualization and sales of configurable products.

Since configurable product consists of multiple parts, that can be combined in various ways, it is the software’s task to help in determining the possible combinations. This gives the user an accurate understanding of the product, and will reed out the most popular configurations by user demand. This would potentially increase sales, and aid the supply chain.

The main concept is that it should be easy for the owners of a product to create a product configuration interface, tailored for their specific product. The end result is an embeddable configuration they can use directly on their site, to make it available to their customers. The customers will see a 3D model of the product where they can pick and choose the parts they want, according to rules defined by the product owners.

The configuration logic is based on a graph algorithm. The algorithm uses forward kinematics and euler rotation to align the chosen parts in 3D. 

#### Technology stack:

* MongoDB, MySQL
* JBoss, EJB3, RestEasy, Weld
* Require.js, Browserify, Gulp, D3, Backbone, WebGL (three.js)
* Vagrant, Salt

