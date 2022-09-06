# Views

Views should be typehinted as `View[MyClient]` or `View[Client]` (when the client is unknown).

## Items

(This includes all items, such as buttons, select menus, etc. Replace Item with the class where applicable)

Items are the basic building blocks of a view. They should always be typehinted as `Item[MyView]` or `Item[View]` (when the view is unknown).

### Example

```py
from nextcord.ui import Item, View

class MyItem(Item):
    ...


class MyView(View):
    def __init__(self, item: MyItem[MyView]):
        super().__init__()
        self.add_item(MyItem("My Item"))



```

<!-- Rant:
Why the hell do items require a view generic. 
They can be used in modals where they don't get a view.
The view isn't even added to the item until the item is added to a view.
Then of course the view has to un-namemangle the items .__view because this is discord.py or whatever remember. 
-->