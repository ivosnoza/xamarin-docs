---
layout : post
title : Toolbar Customization | SfImageEditor | Xamarin.Forms | Syncfusion
description : This section describes how to customize the toolbar items appearance, height, colorpalette and visibility.
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# Toolbar customization

You can customize the color palette, visibility, and appearance of each toolbar item.

## Customize toolbar items

The image editor control provides support to customize and configure the appearance of toolbar menu. You can customize the toolbar by adding respective FooterToolbarItem and HeaderToolbarItem.

### Toolbar item

You can customize each toolbar item using the `Text` and `Icon` properties.

### Name

You can get or set the names of built-in toolbar and dynamically added toolbar items using the `Name` property.

{% highlight C# %}

            public MainPage()
            {			
                InitializeComponent();
                SfImageEditor editor = new SfImageEditor();
                var itemName = editor.ToolbarSettings.ToolbarItems[2].Name;
            }

{% endhighlight %}

N> The following built-in toolbar item names are available in image editor: `Back`, `Text`, `Add`, `TextColor`, `FontFamily`, `Arial`, `Noteworthy`, `Marker Felt`, `Bradley Hand`, `SignPainter`, `Opacity`, `Path`, `StrokeThickness`, `Colors`, `Opacity`, `Shape`, `Rectangle`, `StrokeThickness`, `Circle`, `Arrow`, `Transform`, `Crop`, `free`, `original`, `square`, `3:1`, `3:2`, `4:3`, `5:4`, `16:9`, `Rotate`, `Flip`, `Reset`, `Undo`, `Redo`, and `Save`.

N> You cannot modify the names of existing built-in toolbar items and cannot create toolbar item with these list.

The toolbar menu contains a set of header and footer menu items that help to perform editing actions. This can be categorized into the following types:

1. HeaderToolbarItem
2. FooterToolbarItem
3. SubItems

## Adding HeaderToolbarItem

The `HeaderToolbarItem` is placed on the top of the image editor, and you can customize the header toolbar item using the `Icon` and `Text` properties:

{% highlight C# %}

            editor.ToolbarSettings.ToolbarItems.Add(new HeaderToolbarItem() { Icon = ImageSource.FromResource("ImageEditor.share.png"), Text="Share" });

{% endhighlight %}

## Adding FooterToolbarItem   

The `FooterToolbarItem` is placed on the bottom of the image editor, and you can customize the footer toolbar item using the `Icon` and `Text` properties.

Refer to the following code snippet to customize footer toolbar item.

{% highlight C# %}

            editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() { Icon = ImageSource.FromResource("ImageEditor.delete.png"), Text="Delete" });
            editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() { Icon = ImageSource.FromResource("ImageEditor.more.png"), Text="More" });

{% endhighlight %}

## Adding SubItems to the FooterToolbarItem

The `SubItems` is only applicable for `FooterToolbarItem`, and it represents grouped action of respective footer toolbar item. The SubItems will be placed above the footer toolbar item layout, and you can also customize the appearance of sub items as main toolbar items.

Refer to the following code snippet to customize sub items of footer toolbar item.

{% highlight C# %}

 	editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem()
            {
                Text = "More",
                Icon = ImageSource.FromResource("ImageEditor.Image.more.png"),
                SubItems = new ObservableCollection<ToolbarItem>()
                {
                   new ToolbarItem() {
                Icon = ImageSource.FromResource("ImageEditor.Image.download.png")
                },
                   new ToolbarItem() {
                Icon = ImageSource.FromResource("ImageEditor.Image.share.png")
                } }
            });

{% endhighlight %}

N> You can remove the existing toolbar items [names](/xamarin/sfimageeditor/toolbarcustomization#name) from image editor toolbarItems collection based on the index value and change the icon and text values dynamically for any of the already added toolbar item based on the index as shown in the following code snippet.

{% highlight C# %}

editor.ToolbarSettings.ToolbarItems[5].Text = "new item";
editor.ToolbarSettings.ToolbarItems[3].Icon = ImageSource.FromResource("ImageEditor.Image.jpg");

{% endhighlight %}


## ToolbarItemSelected event 

Whenever you tap the toolbar menu item, the `ToolbarItemSelected` event will be triggered, and you can get the respective tapped toolbar item as an argument as shown in the following code snippet. 

{% highlight C# %}

        public MainPage()
        {
            editor.ToolbarSettings.ToolbarItemSelected += ToolbarSettings_ToolbarItemSelected;
        }

        private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
        {
           DisplayAlert("Selected ToolbarItem is  " + e.ToolbarItem.Text, "Ok", "Cancel");
        }

{% endhighlight %}

### MoveSubItemsToFooterToolbar 

The `MoveSubItemsToFooterToolbar` is boolean property of the ToolbarItemSelected event argument; it decides the placement of each sub items of respective footer toolbar item. 

If you set the value to `true`, the respective sub items of footer item will be placed on footer toolbar layout. If you set `false`, then the sub items will be placed above the footer toolbar layout.

{% highlight C# %}

    public MainPage()
            {
                        . . .

                SfImageEditor edit = new SfImageEditor();
                edit.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem()
                    {
                        Text = "NewFooterItem",
                        SubItems = new ObservableCollection<ToolbarItem>()
                        {
                            new ToolbarItem(){ Text= "Subitem1"},
                            new ToolbarItem(){ Text= "Subitem2"},
                            new ToolbarItem(){ Text= "Subitem3"},
                        }
                    });
                edit.ToolbarSettings.ToolbarItemSelected += ToolbarSettings_ToolbarItemSelected;
                        
                        . . .
            }


    private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
            {
                if(e.ToolbarItem != null && e.ToolbarItem is FooterToolbarItem)
                {
                    if(e.ToolbarItem.Text == "NewFooterItem")
                    {
                        e.MoveSubItemsToFooterToolbar = false;
                    }
                }
            }

{% endhighlight %}

N> This is not applicable for built-in footer toolbar items.

## To hide/show toolbar

To show or hide the toolbar, set the `IsVisible` property of toolbar to either true or false. By default, the `IsVisible` property is set to true.

{% tabs %}

{% highlight XAML %}
  
     <imageeditor:SfImageEditor.ToolbarSettings>
			<imageeditor:ToolbarSettings IsVisible="false" />
		</imageeditor:SfImageEditor.ToolbarSettings>
      
{% endhighlight %}

{% highlight C# %}

      editor.ToolbarSettings.IsVisible = false;
     

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/toolbarvisibility.png)


## To hide/show the toolbar item

You can hide or show the toolbar items by specifying their icon names and setting the boolean values to true or false.

N> You can customize an icon by specifying its [names](/xamarin/sfimageeditor/toolbarcustomization#name).

{% tabs %}

{% highlight C# %}

    editor.SetToolbarItemVisibility("text,save", false);

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/Toolbaritemvisibiliy.png)


## To customize the ColorPalette

You can change the default colors of the ColorPalette in toolbar.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor.ColorPalette>
			<Color>Yellow</Color>
			<Color>Pink</Color>
			<Color>Violet</Color>
		</imageeditor:SfImageEditor.ColorPalette>  
      
{% endhighlight %}

{% highlight C# %}

    ObservableCollection<Color> CustomColorPalette = new ObservableCollection<Color>()
	{
				Color.Yellow,
				Color.Pink,
				Color.Violet
	};

			editor.ColorPalette = CustomColorPalette;

{% endhighlight %}

{% endtabs %}

## Default Color Selected Index

You can change the default index of the color palette in toolbar. By default, color palette index value is 2.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor x:Name="editor" DefaultSelectedColorIndex="0"/>
      
{% endhighlight %}

{% highlight C# %}

    editor.DefaultSelectedColorIndex = 0;

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/DefaultColorSelectedIndex.jpg)

## ToolbarHeight Customization

You can customize `height of the toolbar` and toolbar items `icon` and `text`.

### Customize toolbar height 

The image editor control supports to customize the default height of the `Header`, `Footer`, and `Sub item` using the following properties:

1. HeaderToolbarHeight
2. FooterToolbarHeight 
3. SubItemToolbarHeight

The toolbar items will be resized based on the height. To change the height of the toolbar, refer to the following code snippet.

{% tabs %}

{% highlight XAML %}

         <imageeditor:SfImageEditor.ToolbarSettings>
                    <imageeditor:ToolbarSettings 
                        HeaderToolbarHeight="70"
                        FooterToolbarHeight="70"                          
                        SubItemToolbarHeight="70"/>
                </imageeditor:SfImageEditor.ToolbarSettings>

{% endhighlight %}

{% highlight C# %}

    editor.ToolbarSettings.HeaderToolbarHeight = 70;
    editor.ToolbarSettings.FooterToolbarHeight = 70;
    editor.ToolbarSettings.SubItemToolbarHeight = 70;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/ToolbarHeightCustomization.png)

### Individual toolbar item height customization

You can arrange the toolbar items based on the toolbar height using the following properties:

1.  TextHeight
2.  IconHeight

To change the toolbar item Text and Icon height, refer to the following code snippet.

{% tabs %}

{% highlight C# %}

     FooterToolbarItem footerItem = new FooterToolbarItem()
            {
                IconHeight=40,
                TextHeight=20,
                Icon = ImageSource.FromResource("ImageEditor.share.png"),
                Text = "Share"
            };

            editor.ToolbarSettings.ToolbarItems.Add(footerItem);
    
{% endhighlight %}

{% endtabs %}