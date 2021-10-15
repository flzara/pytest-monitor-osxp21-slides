# Monitor your Python tests to optimise your code!
WIP
---

## WhoAmI

Jean-Sébastien Dieu
Architect @ CFM
Open Source Experience 2021

---

## Agenda

- Pytest-monitor
  - Use case concret détaillé

- Monitor-server
  - extraction de data, le script et le graph.
  - Illustration chez CFM => revoir la CI.

--- ---

# Pytest-monitor

Let's consider a resource critical function whose job is to check a number primality. 

Questions
 * how do we monitor the resource consumption ?
 * how do we compare resource usage between runs ?

---

A possible test would be:

```python
from my_package import is_prime

@pytest.mark.parametrize('nums', [2, 3, 997, 104743, 982451653])
def test_prime(nums):
    assert is_prime(nums)
```
---

## Pytest-monitor  

Slide 2.1

---

## Pytest-monitor conclusion

Slide 2.2

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