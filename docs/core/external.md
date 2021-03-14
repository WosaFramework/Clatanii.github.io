# External Scripts
Looking to add in your own libraries and use them for the core and other resources? In this page you will learn on how to do exactly that!

#### Installing Libraries
To keep all of our "external" libraries sorted and kept track of we have a [specified](https://github.com/WosaFramework/Framework/tree/master/wosa_core/scripting/scripting_ex) folder for placing libraries or external scripts. As you can see libraries such as **RageUI** exist there. By having all of our integrated libraries we depend on inside one directory we can more easily maintain and keep track of them. When installing a new library please always place them in the specified directory.

#### Using Libraries
Using libraries in the same resource is pretty straight forward but what about using them from another resource? You can include files from another resource by using the `@` like this. This is an example from using the **RageUI** files from wosa_core library. From our knowledge `@` does not support usage of the wildcards yet, Therefor you need to add file by file.

```Markdown
client_scripts {
    '@wosa_core/scripting/scripting_ex/RageUI/RMenu.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/RageUI.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/Menu.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/MenuController.lua',

    '@wosa_core/scripting/scripting_ex/RageUI/components/Audio.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/components/Rectangle.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/components/Screen.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/components/Sprite.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/components/Text.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/components/Visual.lua',

    '@wosa_core/scripting/scripting_ex/RageUI/elements/ItemsBadge.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/elements/ItemsColour.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/elements/PanelColour.lua',

	'@wosa_core/scripting/scripting_ex/RageUI/items/UIButton.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/items/UICheckBox.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/items/UISeparator.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/items/UIList.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/items/UIProgress.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/items/UISlider.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/items/UISliderHeritage.lua',
	'@wosa_core/scripting/scripting_ex/RageUI/items/UISliderProgress.lua',
	
	'@wosa_core/scripting/scripting_ex/RageUI/panels/UIBoutonPanel.lua',
	'@wosa_core/scripting/scripting_ex/RageUI/panels/UIColourPanel.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/panels/UIGridPanel.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/panels/UIGridPanelHorizontal.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/panels/UIGridPanelVertical.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/panels/UIPercentagePanel.lua',
    '@wosa_core/scripting/scripting_ex/RageUI/panels/UIStatisticsPanel.lua',

    '@wosa_core/scripting/scripting_ex/RageUI/windows/UIHeritage.lua',
}
```