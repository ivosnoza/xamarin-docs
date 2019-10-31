---
layout: post
title: Features in Syncfusion EffectsView control in Xamarin.Forms
description: This section describes how to use the additional features in Syncfusion EffectsView control in Xamarin.Forms
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Features in SfEffectsView

The [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides the following additional features to enhance the effects:

## FadeOutRipple

By enabling the [`FadeOutRipple`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~FadeOutRipple.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html), the growable circle will lose its opacity to 0 on growing.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    FadeOutRipple="True"
    RippleAnimationDuration="1000">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    FadeOutRipple = true,
    RippleAnimationDuration = 1000
};
            
{% endhighlight %}

{% endtabs %}

![FadeOutRipple](Features_images/EffectsView_Fadeout_Ripple.gif)

## IsSelected

Enabling the [`IsSelected`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~IsSelected.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) sets the view state as selected.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    IsSelected="true"
    LongPressEffects="Selection">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    IsSelected = true,
    LongPressEffects = SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}

## ShouldIgnoreTouches

Enabling the [`ShouldIgnoreTouches`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~ShouldIgnoreTouches.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) cancels the direct interaction of the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html).

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView ShouldIgnoreTouches="true">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    ShouldIgnoreTouches = true
};

{% endhighlight %}

{% endtabs %}

N> On enabling [`ShouldIgnoreTouches`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~ShouldIgnoreTouches.html) property in iOS, the child view will not get interaction.