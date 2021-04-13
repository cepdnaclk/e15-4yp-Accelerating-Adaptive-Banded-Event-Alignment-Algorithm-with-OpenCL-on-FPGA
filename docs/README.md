---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: eYY-4yp-project-template
title:
---

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

# Accelerating-Adaptive-Banded-Event-Alignment-Algorithm-with-OpenCL-on-FPGA

#### Team

- E/15/123, Wishma Herath, [email](mailto:e15123@eng.pdn.ac.lk)
- E/15/280, Pubudu Premathilaka, [email](mailto:pubudu.premathilaka@eng.pdn.ac.lk)
- E/15/316, Suenth Samarasinghe, [email](mailto:e15316@eng.pdn.ac.lk)

#### Supervisors

- Prof Roshan Ragel, [email](mailto:roshanr@eng.pdn.ac.lk)
- Dr Hasindu Gamaarachchi , [email](mailto:hasindu2008@gmail.com)

#### Table of content

1. [Abstract](#abstract)
2. [Related works](#related-works)
3. [Methodology](#methodology)
4. [Experiment Setup and Implementation](#experiment-setup-and-implementation)
5. [Results and Analysis](#results-and-analysis)
6. [Conclusion](#conclusion)
7. [Publications](#publications)
8. [Links](#links)

---

## Abstract
Nanopore sequencing is a third-generation sequencing technology that can analyze long DNA, RNA fragments in real-time. It measures the change in electrical current as nucleic acids pass through a protein nanopore. The Nanopolish software package utilizes the aforementioned signal level changes to obtain useful results in oxford nanopore DNA sequencing. Adaptive Banded Event Alignment (ABEA) is a dynamic programming algorithm used in nanopolish software packages to polish sequencing data and identify nano-strand nucleotides such as measuring DNA methylation. Prior investigations show that ABEA consumes 70% of total CPU time in nanopolish. Thus, optimizing the ABEA algorithm is vital for nanopore sequencing applications. Previous work has deployed accelerated version of ABEA on GPUs using CUDA and has gained improvements on execution time but with high power requirement. With the advancements of HLS (High-Level Synthesis) tools, FPGAs (Field Programmable Gate Arrays) are emerging as accelerators in the field of high performance computing that gives reasonable runtime performance while consuming less power.In this work, we induce a modified version of ABEA for FPGAs using OpenCL. We experimentally identify and adapt optimization techniques to achieve better performance on DE5-net FPGA. We show that our implementation is able to archive  energy consumption of 43% of the previous implementation of ABEA on GPU (f5c). Further, we present performance comparison of our implementations with other different implementations on different platforms in terms of execution time and energy consumption.
## Related works
Previous research, which is done under the objective of accelerating ABEA, deployed an accelerated version of the algorithm on GPUs using CUDA. Their implementation is referred to as *f5c-gpu*. They have achieved 3-5x performance improvement on the CPU-GPU system compared to the original CPU version of the nanopolish software package. Rucci et al. has presented Smith-Waterman (SW) implementation, which is capable of aligning DNA sequences of unrestricted size. In this work, the kernel is implemented using the task parallel programming model. Rucci et al. SW kernel, has exploited inter-task parallelism. They have utilized the SIMD (Single Instruction Multiple Data) vector capability available in the FPGA. 
## Methodology
The host program executes on the CPU and loads the dataset into the main memory. Then, it programs the FPGA, allocates buffers, sets kernel arguments and finally launches the kernels. When FPGA finishes the execution, the host program reads the results from FPGA and stores them in the main memory. The CPU and FPGA use direct memory access (DMA) to transfer data through PCI-e bus. 

OpenCL supports two types of kernels, namely NDRange kernels and Single-Work-Item (SWI) kernels. In the NDRange kernel, OpenCL generates a deep pipeline as a computing unit. All the work-items from all the work-groups execute on that pipeline. The compiler automatically performs work-group pipelining. NDRange kernel has a similar thread hierarchy to CUDA. Each thread is called a work-item, and multiple work-items are grouped to form a work-group. In the SWI kernels, the entire kernel is run by a single work-item, and loop iterations are pipelined to achieve high performance. Initiation Interval (II) is the number of hardware clock cycles a pipeline must wait for before launching the successive loop iterations.
## Experiment Setup and Implementation

## Results and Analysis

## Conclusion

## Publications
1. [Semester 7 report](./)
2. [Semester 7 slides](./)
3. [Semester 8 report](./)
4. [Semester 8 slides](./)
5. Author 1, Author 2 and Author 3 "Research paper title" (2021). [PDF](./).


## Links

[//]: # ( NOTE: EDIT THIS LINKS WITH YOUR REPO DETAILS )

- [Project Repository](https://github.com/imsuneth/abea-on-fpga.git)
- [Project Page](https://cepdnaclk.github.io/repository-name)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)

[//]: # "Please refer this to learn more about Markdown syntax"
[//]: # "https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
