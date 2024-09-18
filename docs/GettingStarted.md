# Getting started with Lithium

First off go ahead and grab a copy of the modules, you can get it from importing the github (will be explained later)
> [!Warning]
> Lithium has to be the parent container of all the modules, it will be broken if that is not the case.

once you have the modules installed where you want: replicated storage or somewhere else you can require() specific modules for specific tasks.

```luau
local Module = require(game:GetService("ReplicatedStorage").Lithium.Toggle)
```

### Toggle

The toggle is used for basic on/off input and will fire a function when its been pressed.
here is how to use the toggle:

>NewToggle takes :ToggleProps

```luau
export type ToggleProps = {
	Text: string,
	Theme: string,
	OnClick: () -> (),
	DefaultOn: boolean
}
```
Below is code that generates a single toggle and places it into a scrolling frame with a UI list layout.

> [!Important]
> The Toggles X size is set to 1,0 so that it fills any scrolling frame its placed into.
> This means that placing it outside a scrolling frame will make it look bad, this can be edited in the INIT module

```luau
local new = toggle.NewToggle({
	Text = "NothingHere",
	Theme = "dark",
	DefaultOn = true,
	OnClick = function(NewValue)
		print(NewValue)
	end,
})
new.GetFrame().Parent = script.Parent
```
now that you know how to create the toggle we can move on.
