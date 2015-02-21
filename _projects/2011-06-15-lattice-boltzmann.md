---
layout: project
title: "Benchmarking Lattice Boltzmann"
modified:
excerpt: "Using CUDA and Python"
date: 2011-06-15
tags: [projects]
image:
  feature: latticeboltzmann.png
  caption: Experiments and results from the project.
---

When deciding on what to work on for topics in my final project, I had only a sense of what I wanted to work with. I had a clear idea that I wanted to learn parallel processing, specifically using CUDA. I got into contact with a faculty professor which had the expertise to guide me in the right way on my path of learning.

My first meeting with him was casual, we talked about a few projects that he had been working on. He warned me that it would be quite a lot to learn during the time I had been allotted to make my project. When I got him convinced that I was determined to take on the task, he pointed me to a piece of paper on his table, having some indistinct code printed on it. When I grabbed it, he started explaining that this was a Matlab script for simulating fluid dynamics and that he would like me to focus on making it parallel using CUDA. Yay! I thought to myself, this is right down my alley.

So I took the paper home and had absolutely no idea about where to start. Looking at the code I felt more confused since I didn't even know Matlab at the time, that was about to change. To my surprise the code is still online and hosted on [exolete's blog](http://exolete.com/lbm/). Untangling the logic in the script and converting it to CUDA proved quite challenging for me, almost to the point where i went mad. But in the end I got a working prototype and some decent results.

When doing the project i read [CUDA by Example](http://www.amazon.com/CUDA-Example-Introduction-General-Purpose-Programming/dp/0131387685). It is a very good and thorough book which has a lot of  great examples. While reading the book i also reworked the examples which really made the knowledge stick, check it out in the [github repository](https://github.com/jiekebo/CUDA-By-Example).

All in all this was a fantastic experience. I had the best, hardest, most frustrating and rewarding time of my life. I also learned that it is not always the result which matters so much as the process itself. I had the privilege of presenting my results to my instructor and a professor from another university at Niels Bohr Institute. I was humbled by the fact that I was presenting my low rung results under the same roof as where some of the pioneers of quantum mechanics wore their soles.

If you are interested in reading the report it is available here [LatticeBoltzmann.pdf]({{ site.url }}/assets/LatticeBoltzmann.pdf). The code is available on [github](https://github.com/jiekebo/Lattice-Boltzmann).