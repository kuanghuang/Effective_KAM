# Part I: Sharp estimates of the constants in inequalities in paradifferential calculus.

1. We use discrete FFT with given N(=1024) and express a function f by its Fourier coefficients.
2. Since it is discrete FFT, the arithmetics are mod N (e.g., 512=-512 mod 1024). Thus, safe operations should not involve frequencies exceeding N//2-1 (511).
3. The Delta_j and S_j operators are straightforward to implement. The product of two functions (f and g) is implemented via the circular convolution (using FFT and inverse FFT), then it is used to calculate the paraproduct. For safe operations, the highest frequency of f + that of g <= N//2-1 (511).
4. To randomly sample a real-valued function f with frequency <= M (256), we utilize np.fft's frequency-ordering, as implemented in ``map_freq``.