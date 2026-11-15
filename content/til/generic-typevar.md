+++
title = "generic TypeVar"
slug = "generic-typevar"
date = 2026-04-15
description = "using generic TypeVar"
taxonomies.categories = ["python3"]
+++

```python3
import random
from typing import TypeVar

T = TypeVar("T")

def get_random(items: list[T]) -> T:
    return random.choice(items)

```

using generic `TypeVar` for type annotationing python code, here we expect a list of Generics (can be anything) but we are ensuring that there is some connection between the input and the output and our editor will be aware of that.
