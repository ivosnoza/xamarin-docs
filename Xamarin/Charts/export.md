---
layout: post
title:  Exporting options in Essential Syncfusion.Xamarin.Forms Chart 
description: How to export the Chart as an image
platform: xamarin
control: Chart
documentation: ug
---

# Exporting

## Export as an image

You can export the Chart as a JPG image using [`SaveAsImage`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SaveAsImage.html#) method of [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html#).

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

chart.SaveAsImage("ChartSample.jpg");

{% endhighlight %}

{% endtabs %}

The exported image will be saved in the different location across the platforms.

**Android** – The image will be saved inside the Pictures directory.

**iOS** – The image will be saved inside the “Photos/Album” directory.

**Windows Phone** – The image will be saved inside the “/Pictures/ Saved Pictures” directory.

N> In order to save the image in Android and Windows Phone, you have to enable the permission to write the file in device storage.

## Get the stream of Chart

['SfChart'](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) contains the following methods to get the chart stream.

## GetStream

The [`GetStream`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~GetStream.html) method of SfChart is used to get the chart as stream. The output stream can be passed as an input of any other components which accept the stream such as pdf, excel, word etc. This method is only applicable for Android and iOS platforms only.

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

chart.GetStream();

{% endhighlight %}

{% endtabs %}

## GetStreamAsync

The [`GetStreamAsync`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~GetStreamAsync.html) method of SfChart is used to get the chart as stream asynchronously. 

N> This method will work only when the SfChart view in UI.

The following code snippet demonstrates the usage of this method:

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

var stream = await chart.GetStreamAsync();

{% endhighlight %}

{% endtabs %}