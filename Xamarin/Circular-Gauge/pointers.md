---

layout: post
title: Pointers in Syncfusion SfCircularGauge control for Xamarin.Forms
description: This section explains the steps required to add and customize pointers in Syncfusion Circular Gauge control for Xamarin.Forms
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# Pointers

You can add multiple pointers to the gauge to point multiple values on the same scale. It is used to show low and high values at the same time. The value of the pointer is set by using the [`Value`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Pointer~Value.html) property.

## Needle pointer

[`Needle Pointer`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer.html) contains three parts, namely needle, knob, and tail and that can be placed on a gauge to mark the values.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
   
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                <gauge:Scale.Pointers>
                     <gauge:NeedlePointer  Value="70" />                     
                </gauge:Scale.Pointers>
				
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
   
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 70;
    scale.Pointers.Add(needlePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Pointer Image](pointers_images/needle-pointer/default.png)

### Setting needle pointer type

The appearance of the needle pointer can be customized by using the [`Type`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~Type.html) property. The default value of this property is [`BarPointer`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.BarPointer.html). This is an enum property, and it has the following options:

1. Bar
2. Triangle

### Setting bar pointer type

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
  
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                <gauge:Scale.Pointers>
                     <gauge:NeedlePointer  Value="60" Type="Bar"/>                    
                 </gauge:Scale.Pointers>
		 
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 60;
	needlePointer.Type = PointerType.Bar;
    scale.Pointers.Add(needlePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Bar Pointer Image](pointers_images/needle-pointer/bar-pointer.png)

### Setting needle pointer type

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
  
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:NeedlePointer  Value="60" Type="Triangle"/>                    
                 </gauge:Scale.Pointers>
		 
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 60;
	needlePointer.Type = PointerType.Triangle;
    scale.Pointers.Add(needlePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Needle Pointer](pointers_images/needle-pointer/needle-pointer.png)

### Needle pointer customization

The length of the needle is controlled by using the [`LengthFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~LengthFactor.html) property. The [`LengthFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~LengthFactor.html) property’s minimum and maximum bounds are 0 and 1. The needle’s UI is customized by using the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Pointer~Color.html) and [`Thickness`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~Thickness.html) properties.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
   
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:NeedlePointer  Value="60" Color="DeepSkyBlue"  LengthFactor="0.7" Thickness="7"/>                   
                 </gauge:Scale.Pointers>
		 
		  </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 60;
    needlePointer.Color = Color.DeepSkyBlue;
    needlePointer.Thickness = 7;      
    needlePointer.LengthFactor = 0.7;
    scale.Pointers.Add(needlePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Needle Customization](pointers_images/needle-pointer/needle-customization.png)

### Knob customization

Knob of the needle pointer can be customized by using the [`KnobColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobColor.html), [`KnobRadius`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobRadius.html), [`KnobRadiusFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobRadiusFactor.html), [`KnobStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobStrokeColor.html), and [`KnobStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobStrokeWidth.html) properties. You can set the radius of knob to pixel and percentage values by using the [`KnobRadius`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobRadius.html) and [`KnobRadiusFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~KnobRadiusFactor.html) properties.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:NeedlePointer  Value="10" KnobRadius="15" KnobStrokeColor="#007DD1"
                                            KnobStrokeWidth="8" KnobColor="White" KnobRadiusFactor="0.1"/>                
                 </gauge:Scale.Pointers>
		 
		  </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
           
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 10;
    needlePointer.KnobRadius = 15;
    needlePointer.KnobStrokeColor = Color.FromHex("#007DD1");
    needlePointer.KnobColor = Color.White;
    needlePointer.KnobStrokeWidth = 8;
    needlePointer.KnobRadiusFactor = 0.1;
    scale.Pointers.Add(needlePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Knob customization](pointers_images/needle-pointer/knob-customization.png)

### Setting tail for needle pointer

Tail of the needle pointer can be customized by using the [`TailColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~TailColor.html), [`TailLengthFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~TailLengthFactor.html), [`TailStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~TailStrokeColor.html), and [`TailStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.NeedlePointer~TailStrokeWidth.html) properties.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                      <gauge:NeedlePointer  Value="90" KnobRadius = "15" TailColor="#757575" TailLengthFactor="0.2" TailStrokeWidth="1" TailStrokeColor="#757575" />              
                 </gauge:Scale.Pointers>
		 
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
 
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 90;
	needlePointer.KnobRadius = 15;
    needlePointer.TailColor = Color.FromHex("#757575");
    needlePointer.TailLengthFactor = 0.2;
    needlePointer.TailStrokeWidth = 1;
    needlePointer.TailStrokeColor = Color.FromHex("#757575");
    scale.Pointers.Add(needlePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Needle Pointer with Tail](pointers_images/needle-pointer/tail.png)

## Range pointer

A range pointer is an accenting line or shaded background range that can be placed on a gauge to mark the values. The [`RangeStart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~RangeStart.html) property allows you to set the starting value of the range pointer.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:RangePointer RangeStart="15" Value="85" />               
                 </gauge:Scale.Pointers>
		 
		      </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    RangePointer rangePointer = new RangePointer();
    rangePointer.RangeStart = 15;
    rangePointer.Value = 85;
    scale.Pointers.Add(rangePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Range Pointer](pointers_images/range-pointer/range-pointer.png)

### Range pointer customization

The range pointer’s UI is customized by using the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Pointer~Color.html) and [`Thickness`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~Thickness.html) properties. First, you should set the `Offset` property for range pointer, and then increase the thickness of the range pointer.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:RangePointer Value="60"  Color="DarkCyan"  Thickness="30" Offset="0.7"/>                
                 </gauge:Scale.Pointers>
		 
		  </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    RangePointer rangePointer = new RangePointer();
    rangePointer.Value = 60;
    rangePointer.Color = Color.DarkCyan;
    rangePointer.Thickness = 30;
    rangePointer.Offset = 0.7;
    scale.Pointers.Add(rangePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Range Pointer Customization](pointers_images/range-pointer/rangepointer-customization.png)

### Setting position for range pointer

The [`RangePointer`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer.html) in the scale can be placed inside or outside of the scale by using the following two ways:

1. The [`Offset`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~Offset.html) property.
2. The [`StartOffset`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~StartOffset.html) and [`EndOffset`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~EndOffset.html) properties.

#### Setting offset for range pointer

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                      <gauge:RangePointer Value="100"  Offset="0.3" Thickness = "30"/>                 
                 </gauge:Scale.Pointers>
		 
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
   
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    RangePointer rangePointer = new RangePointer();
    rangePointer.Value = 100;
    rangePointer.Offset = 0.3;
	rangePointer.Thickness = 30;
    scale.Pointers.Add(rangePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Range Pointer Offset](pointers_images/range-pointer/rangepointer-offset.png)

#### Setting start and end offset for range pointer

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:RangePointer RangeStart="15" Value="85" StartOffset="0.5" EndOffset="0.7"/>                 
                 </gauge:Scale.Pointers>
		 
		  </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
           
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    RangePointer rangePointer = new RangePointer();
    rangePointer.RangeStart = 15;
    rangePointer.Value = 85;
    rangePointer.StartOffset = 0.5;
    rangePointer.EndOffset = 0.7;
    scale.Pointers.Add(rangePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Range Pointer Start and End Offset](pointers_images/range-pointer/rangepointer-start-end-offset.png)

### Setting range cap for range pointer

The [`RangeCap`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~RangeCap.html) property provides options to position the range cap of the [`RangePointer`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer.html), which contains the start, end, both, and none options. The [`RangeCap`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.RangePointer~RangeCap.html) property is an enum property.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
   
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale LabelOffset ="0.75" ScaleStartOffset = "0.9" ScaleEndOffset ="1">

              <gauge:Scale.MajorTickSettings>
                        <gauge:TickSetting Offset = "0.9"/>
                    </gauge:Scale.MajorTickSettings>
                    
                    <gauge:Scale.MinorTickSettings>
                        <gauge:TickSetting Offset = "0.9"/>
                    </gauge:Scale.MinorTickSettings>

                 <gauge:Scale.Pointers>
                      <gauge:RangePointer RangeStart="20" Value="80"  RangeCap="End" StartOffset="0.9" EndOffset ="1" />                  
                 </gauge:Scale.Pointers>
		 
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
           
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    scale.MajorTickSettings.Offset = 0.9;
    scale.MinorTickSettings.Offset = 0.9;
    scale.LabelOffset = 0.75;
    scale.ScaleStartOffset = 0.9;
    scale.ScaleEndOffset = 1;
    RangePointer rangePointer = new RangePointer();
    rangePointer.RangeStart = 20;
    rangePointer.StartOffset = 0.9;
    rangePointer.EndOffset = 1;
    rangePointer.Value = 80;
    rangePointer.RangeCap = RangeCap.End;
    scale.Pointers.Add(rangePointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Range cap](pointers_images/range-pointer/range-cap.png)

## Marker pointer

The different types of marker shapes are used to mark the pointer values in a scale. You can change the marker shape by using the [`MarkerShape`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.MarkerPointer~MarkerShape.html) property. Gauge supports the following types of marker shapes:

* Circle
* Rectangle
* Triangle
* Inverted triangle
* Diamond
* Image

The image is used to denote the pointer value instead of rendering the marker shape. It can be achieved by setting the [`MarkerShape`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.MarkerPointer~MarkerShape.html) to `Image`, and assigning the image path to [`ImageSource`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.MarkerPointer~ImageSource.html) in pointer.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                     <gauge:MarkerPointer Value="70" MarkerShape = "Triangle"/>                  
                 </gauge:Scale.Pointers>
		 
		  </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
    
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    MarkerPointer markerPointer = new MarkerPointer();
    markerPointer.Value = 70;
	markerPointer.MarkerShape = MarkerShape.Triangle;
    scale.Pointers.Add(markerPointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Marker Pointer](pointers_images/marker-pointer/marker-pointer.png)

### Setting image marker shape

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                 <gauge:Scale.Pointers>
                    <gauge:MarkerPointer Value="40" MarkerShape = "Image" ImageSource = "icon.png"/>           
                 </gauge:Scale.Pointers>
		 
		     </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
           
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    ObservableCollection<Pointer> pointers = new ObservableCollection<Pointer>();
    MarkerPointer markerPointer = new MarkerPointer();
    markerPointer.Value = 40; 
    markerPointer.MarkerShape = MarkerShape.Image;
    markerPointer.ImageSource = "icon.png";	
    pointers.Add(markerPointer);
    scale.Pointers = pointers; 
    scales.Add(scale);

    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Marker Image](pointers_images/marker-pointer/image.png)

### Marker pointer customization

The marker can be customized in terms of color, width, and height by using the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Pointer~Color.html), [`MarkerWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.MarkerPointer~MarkerWidth.html), and [`MarkerHeight`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.MarkerPointer~MarkerHeight.html) properties in pointer. First, you should set the `Offset` property for marker pointer, then increase the height and width of the marker pointer.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                <gauge:Scale.Pointers>
                     <gauge:MarkerPointer Value="70" Color="Pink" MarkerHeight="20" MarkerWidth="20" Offset="1"/>                  
                 </gauge:Scale.Pointers>
		 
		    </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	

     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    MarkerPointer markerPointer = new MarkerPointer();
    markerPointer.Value = 70;
    markerPointer.Color = Color.Pink;
    markerPointer.MarkerHeight = 20;
    markerPointer.MarkerWidth = 20;
    markerPointer.Offset = 1;
    scale.Pointers.Add(markerPointer);
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Marker Customization](pointers_images/marker-pointer/markerpointer-customization.png)

### Setting multiple pointers

In addition to the default pointer, you can add n number of pointers to a scale by using the [`Pointers`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Pointer.html) property.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

             <gauge:Scale>

                <gauge:Scale.Pointers>
                    <gauge:MarkerPointer  Value="60" />              
                </gauge:Scale.Pointers>
				
		     </gauge:Scale>
		 
		     <gauge:Scale ShowTicks ="False" ShowLabels ="False" ScaleStartOffset ="0.5" ScaleEndOffset = "0.6">

                 <gauge:Scale.Pointers>           
                    <gauge:NeedlePointer Value="40" LengthFactor = "0.3"/>                  
                  </gauge:Scale.Pointers>
				  
		    </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    ObservableCollection<Pointer> pointers = new ObservableCollection<Pointer>();
    MarkerPointer markerPointer = new MarkerPointer();
    markerPointer.Value = 40;      
    pointers.Add(markerPointer);
	
	Scale scale1 = new Scale();
    scale1.ShowLabels = false;
    scale1.ShowTicks = false;
    scale1.ScaleStartOffset = 0.5;
    scale1.ScaleEndOffset = 0.6;
			
    NeedlePointer needlePointer = new NeedlePointer();
    needlePointer.Value = 60;
    needlePointer.LengthFactor = 0.3;
    pointers.Add(needlePointer);
	
	scale1.Pointers = pointers;
   
    scale.Pointers = pointers; 
    scales.Add(scale);
	scales.Add(scale1);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Circular Gauge Multiple Pointers](pointers_images/marker-pointer/multiple-pointers.png)

### Setting animation for pointer

The [`EnableAnimation`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Pointer~EnableAnimation.html) property is a Boolean property that enables or disables the animation of the pointers in circular gauge.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
     
         <gauge:SfCircularGauge.Scales>

                <gauge:Scale   RimColor="LightGray" RimThickness="30" RadiusFactor="1" ShowTicks="False"
                               StartValue="0" EndValue="100" Interval="10" LabelOffset="0.75" LabelColor="#424242"
                              LabelFontSize ="15" >

                 <gauge:Scale.Pointers>
				 
                      <gauge:RangePointer Color="Orange" Thickness="30" Offset="1" EnableAnimation="True"
                                            AnimationDuration="5" Value="80" />
											
                        <gauge:NeedlePointer Thickness="7" LengthFactor="0.55" Color="LightGray"
                                             KnobColor="White" TailColor="LightGray" TailLengthFactor="0.2"
                                             Type="Triangle"  KnobRadius="12" Value="80"
                                             AnimationDuration="5" TailStrokeWidth="2" TailStrokeColor="LightGray"
                                             KnobStrokeColor="LightGray" KnobStrokeWidth="8"/>			
											 
                 </gauge:Scale.Pointers>
		 
		    </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
   
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Syncfusion.SfGauge.XForms.Scale>();
    Scale scale = new Syncfusion.SfGauge.XForms.Scale();
    scale.RimColor = Color.LightGray;
    scale.RimThickness = 30;
    scale.RadiusFactor = 1;
    scale.ShowTicks = false;
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.LabelOffset = 0.75;
    scale.LabelColor = Color.FromHex("#424242");
    scale.LabelFontSize = 15;

    RangePointer pointer1 = new RangePointer();
    pointer1.Color = Color.Orange;
    pointer1.Thickness = 30;
    pointer1.Offset = 1;
    pointer1.EnableAnimation = true;
    pointer1.AnimationDuration = 5;
    pointer1.Value = 80;
    scale.Pointers.Add(pointer1);

    NeedlePointer pointer2 = new NeedlePointer();
    pointer2.Thickness = 7;
    pointer2.LengthFactor = 0.55;
    pointer2.Color = Color.LightGray;
    pointer2.KnobColor = Color.White;
    pointer2.TailColor = Color.LightGray;
    pointer2.TailLengthFactor = 0.2;
    pointer2.Type = PointerType.Triangle;
    pointer2.KnobRadius = 15;
    pointer2.KnobRadius = 12;
    pointer2.Value = 80;
    pointer2.AnimationDuration = 5;
    pointer2.TailStrokeWidth = 2;
    pointer2.TailStrokeColor = Color.LightGray;
    pointer2.KnobStrokeColor = Color.LightGray;
    pointer2.KnobStrokeWidth = 8;
    scale.Pointers.Add(pointer2);
    circularGauge.Scales.Add(scale);

{% endhighlight %}

{% endtabs %}

![Circular Gauge Pointer Animation](pointers_images/marker-pointer/animation.gif)

### Setting pointer drag

Pointers can be dragged over the scale value. It can be achieved by clicking and dragging the pointer. To enable or disable the pointer drag, use the `EnableDragging` property.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
    
         <gauge:SfCircularGauge.Scales>

              <gauge:Scale   RimColor="DeepSkyBlue" RimThickness="20" RadiusFactor="1" ShowTicks="False"
                               StartValue="0" EndValue="100" Interval="10" LabelOffset="0.75" LabelColor="#424242"
                              LabelFontSize ="15">

                 <gauge:Scale.Pointers>
                    <gauge:MarkerPointer MarkerShape="InvertedTriangle" MarkerHeight="18" MarkerWidth="18"
                                             Value="30" EnableAnimation="False" EnableDragging="True"/>				 
                 </gauge:Scale.Pointers>
		 
		    </gauge:Scale>

         </gauge:SfCircularGauge.Scales>	
  
     </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

           SfCircularGauge circularGauge = new SfCircularGauge(this);
            
            CircularScale scale = new CircularScale();
            scale.RimColor = Color.DeepSkyBlue;
            scale.RimWidth = 20;
            scale.RadiusFactor = 1;
            scale.ShowTicks = false;
            scale.StartValue = 0;
            scale.EndValue = 100;
            scale.Interval = 10;
            scale.LabelOffset = 0.75;
            scale.LabelColor = Color.ParseColor("#424242");
            scale.LabelTextSize = 15;

            MarkerPointer pointer1 = new MarkerPointer();
            pointer1.MarkerShape = Com.Syncfusion.Gauges.SfCircularGauge.Enums.MarkerShape.InvertedTriangle;
            pointer1.Color = Color.DarkBlue;
            pointer1.MarkerHeight = 18;
            pointer1.MarkerWidth = 18;
            pointer1.Value = 30;
            pointer1.EnableAnimation = false;
            pointer1.EnableDragging = true;
            scale.CircularPointers.Add(pointer1);

            circularGauge.CircularScales.Add(scale);

{% endhighlight %}

{% endtabs %}

![Circular Gauge Pointer Drag](pointers_images/marker-pointer/pointer-interaction.gif)