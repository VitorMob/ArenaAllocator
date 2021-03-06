# Arena-mobi

Arena created for project mobi-av disponibilized in github to usage

# Benchmark

Benchmark using [google-benchmark](https://github.com/google/benchmark) 

![BenchMark](assets/Arena-BenchMark.png)

# Tests

Tests using [google-test](https://github.com/google/googletest)

![Test](assets/test_arena.png)

for compile benchmark and tests
```
  mkdir build
  cd build
  cmake ..
  make
```

# Usage Arena

```C
  #include "include/arena.hpp"
  
  Arena fast(3*sizeof(int)); // allocate 3 blocks long from an length int
  
  int main( void )
  {
    // requests blocks
    int *p1 = (int*)fast.req(sizeof(int));
    *p1 = 100;

    int *p2 = (int*)fast.req(sizeof(int));
    *p2 = 400;

    int *p3 = (int*)fast.req(sizeof(int));
    *p3 = 400;
    
    return 0;
  }
```

Functions extras :

```C
void realloc(unsigned int ); // allocate more space in the arena
```
obs: when you make a request for more space the previously created arena will be completely erased and the requested space will be allocated

```C
void dell(); // will put the pointer to the beginning of the arena
unsigned int fquantity(); // will bring the value of available space in the arena
```

# Diagrama

![arenaDigrama](assets/arena_image_1.jpg)
