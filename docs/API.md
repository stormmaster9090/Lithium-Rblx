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

Toggles will also display their current value via text on the button
```luau
-- True:
Text = "On"

-- False :
Text = "Off"
```
Note: make sure to pass a function with a parameter (e) or (newvalue) if you dont a default function will be used

> [!Note]
> .ChangeText() and .GetFrame() are in the process of being changed to a Method, and allowing for other parameters to be passed on the former

#### Creating for plugins
Lithium is primarily designed for plugins but the module lacks any use of settingd() for the specific reason that a person may want to use lithium to create ingame UI

To accurately get the users current studio theme and create UI accordingly to it you could do this
> Do note that :ChangeTheme(Theme: string) is in progress.

```luau
local Theme = settings().Studio.Theme
if Theme == "light" then
local new = toggle.NewToggle({
	Text = "NothingHere",
	Theme = "light",
	DefaultOn = true,
	OnClick = function(NewValue)
		print(NewValue)
	end,
})
end
-- this will create a light toggle
```
It is advisable that you listen the ThemeChanged Event so that you can refresh the UI

## Color3 Selector

The Color3 Selector allows users to input numbers into 3 boxes to respectively create a Color3 value.
The .NewColor3 takes selectorprops.

### Type: SelectorProps
| PropParam  | Type |
| ------------- | ------------- |
|  DefaultColor  |  Color3  |
|  Theme  | String  |
|  OnChange  | () -> ()  |

### Type: Color3Selector

| PropParam  | Type |
| ------------- | ------------- |
|  OnChange  |  () -> (Color3)  |
|  ChangeColor  | (Color3) -> ()  |




