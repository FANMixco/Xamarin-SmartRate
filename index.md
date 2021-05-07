<a href="https://github.com/sponsors/FANMixco/" target="_blank">
   <img src="https://i.stack.imgur.com/zoyl1.png" alt="sponsor" />
</a>

# Xamarin-SmartRate

## Get it

|  Package  |Latest Release|
|:----------|:------------:|
|**Xamarin-SmartRate**|[![NuGet Badge Xamarin-SmartRate](https://buildstats.info/nuget/Xamarin-SmartRate)](https://www.nuget.org/packages/Xamarin-SmartRate/)|

A library for simple implementation of smart ranking.
The user will see a dialog every x time.
If the user gives a high score, he will be transferred to the Google store. If he gives a low score, he will only receive a thank you toast message.

<img src="https://raw.githubusercontent.com/guy-4444/SmartRateUsDialog-Android/master/sc_1.png" width="288">
<img src="https://raw.githubusercontent.com/guy-4444/SmartRateUsDialog-Android/master/sc_2.png" width="288">

<img src="https://raw.githubusercontent.com/guy-4444/SmartRateUsDialog-Android/master/sc_5.png" width="512">
<img src="https://raw.githubusercontent.com/guy-4444/SmartRateUsDialog-Android/master/sc_6.png" width="512">

## Usage

## Usage

###### StepProgress Constructor:
```csharp

// For continual calls - 
// first call after 3 days, the dialog will appear every 2 days until the user rates the app / or clicks on NEVER ASK AGAIN button
// the number 4 represents the minimum stars to be shown
// the 48 represents 48h and is going to be shown after 2 days
// the 72 represents 72h delay and the dialog is going to be shown after 3 days more
SmartRate.Rate(this
        , "Rate Us"
        , "Tell others what you think about this app"
        , "Continue"
        , "Please take a moment and rate us on Google Play"
        , "click here"
        , "Ask me later"
        , "Never ask again"
        , "Cancel"
        , "Thanks for the feedback"
        , Color.ParseColor("#2196F3")
        , 4
        , 48
        , 72
);

// For one time call
// it will appear after 3 days by default
// the number 4 represents the minimum stars to be shown
SmartRate.Rate(this
        , "Rate Us"
        , "Tell others what you think about this app"
        , "Continue"
        , "Please take a moment and rate us on Google Play"
        , "click here"
        , "Cancel"
        , "Thanks for the feedback"
        , Color.ParseColor("#2196F3")
        , 4
);

// With Call Back:
SmartRate.Rate(this
        , "Rate Us"
        , "Tell others what you think about this app"
        , "Continue"
        , "Please take a moment and rate us on Google Play"
        , "click here"
        , "Cancel"
        , "Thanks for the feedback"
        , Color.ParseColor("#2196F3")
        , 4
        , new CallBack_UserRating()
        }
);

public class CallBack_UserRating : Java.Lang.Object, ICallBack_UserRating {
            public object void userRating(int rating) {
                // Do something
                // maybe from now disable this button
            }
}

// Self implement without link to google play store:
// -1 on stars
SmartRate.Rate(this
        , Color.ParseColor("#E44643")
        , -1
        , new CallBack_UserRating()
);

```


![device-2018-06-06-144912](https://github.com/guy-4444/SmartRateUsDialog-Android/blob/master/desc.png?raw=true)

## License

    Copyright 2019-2020 Guy Isakov and Federico Navarrete

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

## Credits

5 stars icon:
Icon made by Flat Icons (www.flat-icons.com) from www.flaticon.com
Google play icon:
Icon made by Flat Icons (www.flat-icons.com) from www.flaticon.com
