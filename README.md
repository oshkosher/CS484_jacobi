# CS484_jacobi
Red-Black Jacobi on CPU, GPU, Xeon Phi

The goal of this project was to compare the performance and programmer productivity
while implementing a Red-black Jacobi solver in three forms:
 * Xeon CPU
 * Xeon Phi coprocessor
 * CUDA GPU

Here is the overall performance I was able to get. The test was to do 50 iterations on a 8192x8192 grid of floats, where
each iteration is a red phase and a black phase.

 * Xeon CPU, single thread: 48954 ms
 * Xeon CPU, 12 threads: 1767 ms
 * Xeon Phi coprocessor: 1409 ms
 * CUDA (Titan Z GPU): 441 ms (including time to copy to and from GPU)

Subjective programming difficulty
 * Xeon CPU: straightforward
 * Xeon CPU, threaded: moderate, needed to tune block sizes and synchronization algorithm
 * Xeon Phi coprocessor: still working on it
 * CUDA: hard, many options to test, but simplest solution was quite fast

See "Jacobi presentation.pdf" for details.

