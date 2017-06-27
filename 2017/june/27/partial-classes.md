# Partial Classes
It is possible to split the definition of a class or struct, an interface, or a method over two or more source files. 
The *biggest use* of partial classes is to **make it easier for code generators/designers**.

### Example
**ViewController.designer.cs**
```C#
...

[Outlet]
[GeneratedCode ("iOS Designer", "1.0")]
UIKit.UISwitch switchNight { get; set; }

[Action ("SliderSize_ValueChanged:")]
[GeneratedCode ("iOS Designer", "1.0")]
partial void SliderSize_ValueChanged (UIKit.UISlider sender);

...
```

  
**ViewController.cs**
```C#
...

partial void SwitchNight_ValueChanged(UISwitch sender) {
  if (switchNight.On) {
    this.View.BackgroundColor = UIColor.FromRGB(25, 25, 112);
    buttonStart.TitleLabel.TextColor = UIColor.White;
    nightLabel.TextColor = UIColor.White;
    sizeLabel.TextColor = UIColor.White;
  } else {
    this.View.BackgroundColor = UIColor.White;
    buttonStart.TitleLabel.TextColor = UIColor.Black;
    nightLabel.TextColor = UIColor.Black;
    sizeLabel.TextColor = UIColor.Black;
  }
}

...
```
