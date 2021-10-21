# Monitor your Python tests to optimise your code!

Jean-Sébastien Dieu, Architect @ [CFM](https://www.cfm.fr)

---

## Agenda

* Pytest-monitor
  * Use case concret détaillé

* Monitor-server
  * extraction de data, le script et le graph.
  * Illustration chez CFM => revoir la CI.

--- ---

# Problem setup

Let's consider a resource critical function whose job is to check a number primality.

---

## Questions

* how do we monitor the resource consumption ?
* how do we compare resource usage between runs ?

---

## Pytest-monitor  

* it is a pytest plugin <!-- .element: class="fragment" data-fragment-index="1" data-autoslide="1000" -->
* Few requirements needed (sqlite3, python, memory_profiler and psutils) <!-- .element: class="fragment" data-fragment-index="2" data-autoslide="1000" -->
* Track resources consumed by any test suite <!-- .element: class="fragment" data-fragment-index="3" data-autoslide="1000" -->
    * Memory
    * Compute time
    * etc.
* Historize the results <!-- .element: class="fragment" data-fragment-index="4" -->

---
With pytest, a possible test would be:

```python [1-6]
import pytest
from my_package import is_prime

@pytest.mark.parametrize('nums', [2, 3, 997, 104743, 982451653])
def test_prime(nums):
    assert is_prime(nums)
```

---

## Pytest-monitor results

![Pytest Monitor run in terminal](ptm_run.png)

```sql
sqlite> select ITEM, TOTAL_TIME, CPU_USAGE, MEM_USAGE, ITEM_PATH from TEST_METRICS;
test_sleep1|1.00518894195557|0.0|0.76953125|pkg1.test_mod1
test_heavy|0.00533604621887207|0.0|0.80078125|pkg1.test_mod1
test_heavy|0.00467038154602051|2.14115268773291|0.8125|pkg1.test_mod1
test_heavy|0.00461006164550781|0.0|1.26953125|pkg1.test_mod1
test_heavy|0.0324029922485352|0.925840421461576|1.51953125|pkg1.test_mod1
test_sleep_400ms|0.405560970306396|0.0246572050373711|1.51953125|pkg1.test_mod2
test_master_sleep|5.00535321235657|0.998930502578049|1.51953125|pkg2.test_mod_a
test_method1|0.506380081176758|0.0|1.51953125|pkg3.test_mod_cl
test_force_monitor|5.0064685344696|0.998707964621156|1.51953125|pkg4.test_mod_a
```

--- ---

# Monitor-server-API

Slide 3.0.1

---

## Monitor-server-API introduction

Coucou <!-- .element: class="fragment" data-fragment-index="2" -->

Recoucou <!-- .element: class="fragment" data-fragment-index="1" -->

---

## Monitor-server-API conclusion

Slide 3.2

--- ---

# Questions?
