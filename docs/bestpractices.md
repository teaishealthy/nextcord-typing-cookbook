# Best Practices

## typings.py

When typing your nextcord bot, I'd recommend creating a `typings.py` file.
This file will contain all the typings for your bot.


It should atleast include the following:

```py

from typing import TYPE_CHECKING
from nextcord.ext.commands import Context

if TYPE_CHECKING:
    from .bot import Bot # Import your subclassed bot
    Context = Context[Bot]

```

Now you can import the `Context` type from `typings.py`, this way you don't have to import your main bot file in every file you want to use the `Context[Bot]` type.


## from \_\_future\_\_ import annotations

When typing your bot, I'd recommend using `from __future__ import annotations` and `typing.TYPE_CHECKING` to prevent circular imports.


## Type Checkers

Pyright works well with nextcord, but when using strict mode, you will likely need to add `# type: ignore` to a lot of places.