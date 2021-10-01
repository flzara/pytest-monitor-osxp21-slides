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

Slide 2.0

---

```python
import pytest
import time


# Tests are run and monitored by default: no boilerplate code needed
def test_sleep1():
    time.sleep(1)

# Run as a test, but do not monitor:
@pytest.mark.monitor_skip_test
def test_sleep2():
    time.sleep(2)

# Support for parametrized tests (monitored by default):
@pytest.mark.parametrize(('range_max', 'other'), [(10, "10"), (100, "100"), (1000, "1000"), (10000, "10000")])
def test_heavy(range_max, other):
    assert len(['a' * i for i in range(range_max)]) == range_max
```

---

## Pytest-monitor  introduction

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