---
layout: post
title: "How to download Kaltura videos from Canvas"
date:   2023-05-04 22:22:05 +1000
categories: canvas
---

This post will cover how to download any embedded Kaltura video from Canvas in Firefox.
<br>
<br>
Prerequisites:
- FFMPEG
<p>
Right click the page and click "Inspect". Go to the Network tab and press play on the video. In the Network tab, look for a file that begins with "index.m3u8". There may be more than one for different resolutions.
Select the first one that appears, it will be the one with the highest possible resolution. Otherwise, select another one for a lower resolution.
Right click "Copy Value" then "URL". The URL should look something like this:
</p>
{% highlight url %}
https://cfvod.kaltura.com/scf/hls/p/2300331/sp/230033100/serveFlavor/entryId/1_6stc7su1/v/1/ev/5/flavorId/1_tuorvp43/name/a.mp4/index.m3u8?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jZnZvZC5rYWx0dXJhLmNvbS9zY2YvaGxzL3AvMjMwMDMzMS9zcC8yMzAwMzMxMDAvc2VydmVGbGF2b3IvZW50cnlJZC8xXzZzdGM3c3UxL3YvMS9ldi81KiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTY4MzI5MDA0M319fV19&Signature=Hd4tDxCY7DcX3mSowdcFeEgAuWhsmGDy6~oIJkifvSYDK1ljw-bZXIb8UUclcWLhEnASGd4nnZURWw87pbS6LPLRBjHQya24Dy1WSmLgUSoXuq1Ul8fkhQKVCDWDZtD4p2zpaRtGXlgemaIhmtrvwiYgEowYG70ARRv01hlA86cSCUbfWd4g9Kfk-Z4-FAJXlIVhcyNjjLwWbIHaSSuT56IX9Mo8kW4ihrYMJ5dbPYsQmfqnZ-FBlhLZ-ha8Wc1GLcJRG9dtef9TyI8lEVWU60tE4-LLoa0il7jXI-WOziaQWFlTNFIbaywGri8wZV9uuxsnCbkpV7CTm~QLiqLWFg__&Key-Pair-Id=APKAJT6QIWSKVYK3V34A
{% endhighlight %}
<br>
Use the following command in a terminal, replacing "your-url" with the copied URL to get the video:

{% highlight bash %}
ffmpeg -i "your-url" -c copy out.mp4
{% endhighlight %}
