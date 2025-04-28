- sectioning number with single quote: `int a{1'000'000};`
- polymorphic base class:
```cpp
struct event_base {
  int type;
  explicit event_base(int t) : type(t) {}
  event_base(const event_base&) = default;
  event_base(event_base&&) noexcept = default;
  event_base& operator=(const event_base&) = default;
  event_base& operator=(event_base&&) noexcept = default;
  virtual ~event_base() = default;
};
```

- allow debug attach:
```c
#include <linux/prctl.h>
#include <sys/prctl.h>
prctl(PR_SET_PTRACER, PR_SET_PTRACER_ANY);
```

- static data member cannot be defined in class declaration, unless declared with for `constexpr` and `inline`. Reason: 2 trans unit doing 2 sources, both include a header file with said static member - these 2 sources cannot be compiled to use same object static object since they are separately compiled. [](https://en.cppreference.com/w/cpp/language/static)

-
