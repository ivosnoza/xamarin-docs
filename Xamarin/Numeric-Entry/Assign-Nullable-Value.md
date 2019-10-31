---
layout: post
title: Various features in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in NumericTextBox.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Assign Nullable Value

The null values can be set in SfNumericTextBox `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" AllowNull="true" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();
numericTextBox.AllowNull=true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/allownull.png)

## Set Hint Text

The `WaterMark` property can be used to provide a hint that helps the user to get started with their input. The watermark text is visible when value is empty or null.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" AllowNull = "true"  Watermark="Getting Started" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox  numericTextBox=new SfNumericTextBox();
numericTextBox.Watermark = "Getting Started";
numericTextBox.AllowNull = true;
this.Content=numericTextBox;
	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted1.png)

For customizing the color of NumericTextBox's Watermark [refer](https://help.syncfusion.com/xamarin/sfnumerictextbox/colors)