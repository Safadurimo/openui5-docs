<!-- loio3b718b5372fa457c92cf5087a673e953 -->

| loio |
| -----|
| 3b718b5372fa457c92cf5087a673e953 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3b718b5372fa457c92cf5087a673e953) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3b718b5372fa457c92cf5087a673e953)</div>

## Responsive Paddings Enablement

Apply responsive paddings over separate parts of the controls.

> Note:
> Responsive paddings can be enabled only when using the SAP Quartz theme.
> 
> 

***

<a name="loio3b718b5372fa457c92cf5087a673e953__section_d2f_1pv_jjb"/>

### Usage

As a control developer you can apply responsive paddings over separate parts of the controls, when using the SAP Quartz theme. The `sap.ui.core.util.ResponsivePaddingsEnablement` allows the breakpoints and layout paddings to be determined by the container's width.

***

#### How to Enable Responsive Paddings

Here is an example how to implement the utility when developing a control:

```
ResponsivePaddingsEnablement.call(MyCustomControl.prototype, {
					header: {suffix: "-myCustomControlHeader"},
					content: {selector: ".myCustomControlContent"}
					});
				
```

As the example demonstrates, there are two ways to select an element:

-   Using suffix: when you need to select an element by its ID;
-   Using selector: covers all possible CSS selections;

To call the utility, when initializing the control use:

```
MyCustomControl._initResponsivePaddingsEnablement()
```

***

#### Applied Paddings

Based on the container’s size one of the following classes is added, and the corresponding padding-left and padding-right are applied:

|Container size \(pixels\)|Class|Padding-Left and Padding-Right Applied|
|-------------------------|-----|--------------------------------------|
|<= 600|sapM-Std-PaddingS|1rem|
|\>600|sapM-Std-PaddingM|2rem|
|\>1024|sapM-Std-PaddingL|2rem|
|\>1440|sapM-Std-PaddingXL|3rem|

***

#### Supported Controls

The following list shows examples of controls that support the responsive paddings:

-   `sap.m.Page`
-   `sap.m.Popover`
-   `sap.m.Wizard`

To enable this concept and add responsive paddings to an element of the controls, you may add the following classes to the controls, depending on your use case:

|`sap.m.Page`|`sap.m.Popover`|`sap.m.Wizard`|
|------------|---------------|--------------|
| `sapUiResponsivePadding—header` `sapUiResponsivePadding—subHeader` `sapUiResponsivePadding—content` `sapUiResponsivePadding—footer` `sapUiResponsivePadding—floatingFooter` | `sapUiResponsivePadding—header` `sapUiResponsivePadding—subHeader` `sapUiResponsivePadding—content` `sapUiResponsivePaddin—footer` | `sapUiResponsivePadding—header` `sapUiResponsivePadding—content` |

***

```
<Page class="sapUiResponsivePadding--header sapUiResponsivePadding--subHeader sapUiResponsivePadding--content sapUiResponsivePadding--footer sapUiResponsivePadding--floatingFooter">
```

For a detailed example, see the [Samples for `sap.m.Page`](https://openui5.hana.ondemand.com/#/entity/sap.m.Page). 
