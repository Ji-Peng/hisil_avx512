# montgomery4x

The original [project](https://github.com/crypto-ninjaturtles/montgomery4x/tree/master/avx512-5limb-4x2) can not be used.

We made some small changes to make it compile and run.

```bash
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make
./hisil_avx512_test
```

The performance on my machine:
scalar_mult_var_base      :  22 µs,  43641.9 oper/s,  61867 cycles/op, diff=2023102.579889

The code size can be computed by run the command.
```bash
nm hisil_avx512_test --print-size --size-sort --radix=d | awk '{$1=""}1' | awk '{sum+=$1 ; print $0} END{print "Total size =", sum, "bytes =", sum/1024, "KB"}' > hisil_avx512_test.size
```
Total size = 12006 bytes = 11.7246 KB