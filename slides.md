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

* Faire le run du test.
* Montre un run pytest avec monitor
* faire une query dans la base pour montrer des résultats.

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
