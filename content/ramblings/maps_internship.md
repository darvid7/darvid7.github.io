+++
title = "Google Maps 2017 - 2018 Summer Internship"
date = 2018-07-10T19:48:13+10:00
draft = false
tags = [
	"google", 
	"maps", 
	"android",
	"java" 
]
categories = [
	"tech"
]
+++
Over the past summer (2017 - 2018) I worked on the [Google Maps Location Sharing](https://blog.google/products/maps/share-your-trips-and-real-time-location-google-maps/) team! Location Sharing in Maps allows you to share your location with someone. Typical use cases include sharing with family members when overseas and sharing with friends to try meet up somewhere. I worked on two features to improve the user experience when sharing location by providing more information to the person being shared with, I can now talk about because they launched! 

Previously the information on the card displayed when sharing your location included stuff such as your distance, directions to them, how old it is and if you are sharing with them.

The first feature was to display the sharer's battery when it is low. The second feature was to display the sharer's local time. The project can be broken down into the following steps.

1. Location the battery information from the Maps backends and plumb it through the RPC stack
2. Show the battery information on the android application
4. Make server side changes for time zone
5. Show the time zone information on the android application 

It seems fairly straight forward when broken down like that, but there were a few large caveats.

1. The Maps backend comprised of many (between 1 and 10) different backend services, some of which were owned by teams in Mountain View, USA. 
2. The backends used lots of dependency injection ([Guice](https://github.com/google/guice), [Dagger](https://google.github.io/dagger/) and lots of [producer modules](https://google.github.io/dagger/producers.html) which implement asynchronous dependency injection) meaning it was non trivial figuring out how data from once place got to another
4. Finding the right service that handled time zone conversions in the massive code base and handling edge cases such as day light saving and date time boarders 

Not to mention the learning curve ramping up to Google's internal tooling, version control, abundance of protobuffers and internal libraries, notably Google uses an internal library to create android UIs rather than xml.

I had to work with UX designers to make sure the product was consistent across Google products. UX Writers approved my strings to ensure phrasing was correct and translations to over 50 languages were acceptable as some languages phrase sentences differently structurally. I bugged product managers push the feature through to our beta and alpha release stages ensuring features were sufficiently tested and complied with legal, privacy and security. As well as some interesting technical considerations such as when to store information to disk and when to drop information that I usually don't think about on the outset of the project. The tech used was  Java (Guice, Dagger2, Android), protobuffers and RPCs.
<br/>
<span style="display: -webkit-inline-box;" >
	<img src="/images/blog/maps_internship/battery.jpg" width="300px" style="padding: 10px
    "/>
	<img src="/images/blog/maps_internship/timezone.jpg" width="300px" style="padding: 10px 
    "/>
</span>
<br/>

I can now point elements (<span style="color: red;">red box</span> around them) of the Google Maps Mobile Application and proudly say I did that.

Along the day I learnt how to make coffee & froth milk!! ☕And also broke a surf board 🌊
<span style="display: -webkit-inline-box;" >
	<img src="/images/blog/maps_internship/coffee.jpg" width="225px" height="300px"  style="padding: 10px"/>
	<img src="/images/blog/maps_internship/surfboard.jpg" width="225px" height="300px" style="padding: 10px"/>
</span>