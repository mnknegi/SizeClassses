# SizeClassses

A demo to illustrate how size classes works.

## Size Classes using Interface builder

- The easiest and most convenient approach for implementing size classes is generally using interface builder.
- One can simply assign layouts and constraints to a specific size classes in interface builder and the layout will change according to the change in the size classes.

In this demo we are going to display the title and the body of the text by doing some customization for different size classes.

I have choosen two device types - iPhone 14 Pro and iPad Pro 11

### iPhone 14 Pro
Portrait size classes: w: `Compact`, h: `Regular`
Landscape size classes: w: `Compact`, h: `Compact`

### iPad Pro 11
Portrait size classes: w: `Regular`, h: `Regular`
Landscape size classes: w: `Regular`, h: `Regular`

## Customization

#### **iPhone 14 Pro**

- The `Title` label font size is `Title 1`, Color is `Label Color`.
- The body TextView font size is `System 14.0`, Color is `Label Color`. Margin for top, left, right and bottom is `standard`, `8.0`, `8.0`, `8.0` respectively.

Now click on the device configuration bar and select iPad from there, this will present a list of iPads for you. click on iPad Pro 11 and see the UI layout. The layout doesn't look great on the iPad. To resolve this, we will do some customization with the UI using size classes.

#### **iPad Pro 11**
 
Click on the iPad Pro 11 from deivce configuration bar and then click on the title label. The font size will be same for this label in iPad as well(i.e. Title 1). We want a bigger title font in iPad. For this
- Click on the grey plus symbol to the left of the font attribute. Selecting the plus symbol gives you the opportunity to add a cusomized value for a size class. After selecting the plus symbol you can select the size class you are interested in i.e. width, height or Gamut.
- Select Regualr width and Regular height for iPad and after adding this a new customized value will appear for the font attribute.
- For title provide `System 55.0` as the font size for wR hR. This will set the title font size System 55.0 to iPad title label or the device whose configuration is wR hR. And provide `System Red Color` as the text color for new color attribute wR hR after repeating the same process for Color attribute as well.
- For body TextView select the font size `System 25.0` and color `System Green Color` for wR hR.
- Modify the Margin for TextView with the same process by adding additional attribute for left and right anchor and provide the value for the constraints to `50.0`. This will show additional margin for iPad from left and right safe area layout.

#### Installing and uninstalling a view or constraint

Now we are going to add a subtitle label for the iPad users. The subtitle will be visible only for the device with the wR hR size class configuraiton.
- We will select iPad and drag a label inside our ViewController in storyboard. 
- In attribute inspector provide the font size `System 30.0` to the subtitle label.
- After this scroll up and you will see a checkbox with title `installed`. Click on the plus button infront of it and select `Regular` width and `Regualr` height.
- This will add another attribute in that section. Disable the default one and keep the wR hR one enabled. This will make the subtitle label visible for iPad only or the device with wR hR configuartion. For iPhone it will not be visible.

Now the subtitle view needs to be in between title and body. For this we need to do below adjustments.
- Select iPhone 14 Pro from the device configuration bar and select the body TextView. Click on top anchor and select it. This will open the constraints detail in size inspector.
- From there click on `+` symbol infront of `installed` and select wR hR.
- Keep the checkbox `enabled` for `default` and `disable` the checkbox for wR hR. This will remove this constraints with device size classes wR hR.
- Now select iPad from device configuration bar and provide constraints to subtitle view top and bottom from title and body text.
- Repeat the same thing as above mention with a slight difference. This time uncheck default and check the wR hR as we want this constraints for the iPad.

iPhone 14 Pro
![iPhone 14 Pro]()
