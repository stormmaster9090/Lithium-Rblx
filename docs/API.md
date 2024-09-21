# Full Lithium API

you can view the getting started file to understand the main idea.
## Toggle

### Type: ToggleProps
| PropParam  | Type |
| ------------- | ------------- |
|  Text  |  String  |
|  Theme  | String  |
|  OnClick  | () -> ()  |
|  DefaultOn  | Boolean  |


### Type: Toggle
| PropParam  | Type |
| ------------- | ------------- |
|  GetFrame  |  () -> (GuiObject)  |
|  ChangeText  | (String) -> ()  |
|  OnClick  | () -> (Boolean)  |

### Creating a new toggle

You can use the following code to create a new toggle with the defined variables inside the prop.
here is an example.
```luau
local toggle = require(game.ReplicatedStorage.Lithium.Toggle)

local new = toggle.NewToggle({
	Text = "NothingHere",
	Theme = "dark",
	DefaultOn = true,
	OnClick = function(NewValue)
		print(NewValue)
	end,
})
```
All parameters are mandatory.

You can get the toggle UI by calling ```.GetFrame()``` 
```luau
new.GetFrame().Parent = script.Parent
```

You can change the text of the toggle with ```.ChangeText(str)```
```luau
new.ChangeText("hello)
```
> [!Important]
> Upon the creation of a Toggle object all of the functionality is handled within the module,
> this is more convinient but harder to customize

