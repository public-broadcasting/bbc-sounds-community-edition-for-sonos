# BBC Sounds (Community Edition) for Sonos

In December 2021 [BBC Sounds](https://support.sonos.com/services/bbc-sounds) launched in the [Sonos app]((https://www.sonos.com/controller-app)). Listeners with Sonos speakers in the UK are able to enjoy BBC radio, music mixes and podcasts, using the Sonos app.

Listerners outside the UK have to fall back on the <a href="https://support.sonos.com/services/radio-by-tunein">TuneIn</a>  integration or <a href="https://www.sonos.com/sonos-radio">Sonos Radio</a>, which relys on TuneIn. The <a href="https://www.bbc.co.uk/sounds/help/questions/recent-changes-to-bbc-sounds/shoutcast-closure">BBC streams</a> available on TuneIn occasionally <a herf="https://www.bbc.co.uk/sounds/help/questions/recent-changes-to-bbc-sounds/shoutcast-closure">play an announcement indicating that</a> the streams are outdated and <a href="https://www.bbc.co.uk/sounds/help/questions/recent-changes-to-bbc-sounds/shoutcast-closure">will stop working in mid-2023</a>. There is no way to have the streams updated to get rid of the message.

Besides the alternative of downloading the BBC sounds app for <a href="https://apps.apple.com/app/bbc-sounds/id1380676511">iOS</a>/<a href="https://play.google.com/store/apps/details?id=com.bbc.sounds">Android</a> and transferring it to Sonos via <a href="https://support.sonos.com/article/stream-airplay-audio-to-sonos">AirPlay</a>, <a href="https://support.sonos.com/article/use-bluetooth-on-sonos">Bluetooth</a> or <a href="https://support.sonos.com/article/use-line-in-on-sonos">Line-In</a> (based on the specs of the existing speakers), there are also options to <a href="https://support.sonos.com/article/add-an-internet-radio-station-to-sonos">manually add the desired radio station</a> to Sonos.

**BBC Sounds (Community Edition)** bring back the classic Sonos control in order to listen to your favorite stations, without the hassle of using third-party apps and cast technologies.

---

## Installation

1.) Get the IP Address of one of your speakers

&nbsp;&nbsp; Sonos App for iOS/Android: `Settings` -> `System` -> `About My System`<br>
&nbsp;&nbsp; Sonos App for macOS: `Sonos` -> `About My System`<br>
&nbsp;&nbsp; Sonos App for Windows: `Help` -> `About My System`

<img src="https://raw.githubusercontent.com/public-broadcasting/bbc-sounds-community-edition-for-sonos/main/img/about_my_system.jpg" alt="About My System" width="236" height="483">


In this example the IP Address of the speaker is `192.168.0.156`. For the following steps, replace the IP Address shown here with the IP Address shown in the app.

2.) Open the custom service descriptor page by opening the web address below with a web browser of your choice:

http://`192.168.0.156`:1400/customsd (Replace the IP Address shown here.)

3.) Fill out all fields as shown below:

**Tip:** For a better view download the <a href="https://github.com/public-broadcasting/bbc-sounds-community-edition-for-sonos/edit/main/README.md">HMTL file</a>.

&nbsp;&nbsp; 3.1 SID: Enter `255`<br>
&nbsp;&nbsp; ℹ️ If you already have a CustomSD, then switch to one of 240-253.<br>

&nbsp;&nbsp; 3.2 Service Name (leave blank to erase): Enter `BBC Sounds (Community Edition)`<br>
&nbsp;&nbsp; ℹ️ You can also specify a name of your choice.

&nbsp;&nbsp; 3.3 Secure Endpoint URL: Enter `https://smapi.streamurl.link/`

&nbsp;&nbsp; 3.4 Polling interval (seconds): Enter `300`

&nbsp;&nbsp; 3.5 Authentication SOAP header policy: Choose `Anonymous`

&nbsp;&nbsp; 3.6a Strings table (optional) - Version: Enter `0`<br>
&nbsp;&nbsp; 3.6b Strings table (optional) - Uri: Enter `https://smapi.streamurl.link/strings.xml`

&nbsp;&nbsp; 3.7a Strings table (optional) - Version: Enter `0`<br>
&nbsp;&nbsp; 3.7b Strings table (optional) - Uri: Enter `https://smapi.streamurl.link/pmap.xml`

&nbsp;&nbsp; 3.8  Container Type: Choose `Music Service`

&nbsp;&nbsp; 3.9  Capabilities - Search: Check the option `Search`

&nbsp;&nbsp; 3.10  Capabilities - Extended Metadata: Check the option `Extended Metadata (More Menu, Info & Options)`

Press the `submit` button after you have filled in the fields.

The settings should look like this screenshot:

<img src="https://raw.githubusercontent.com/public-broadcasting/bbc-sounds-community-edition-for-sonos/main/img/customsd_setup.jpg" alt="About My System" width="519" height="445">

4.) Add the service as a music service

You will notice that you now have an additional music service to choose from.

<img src="https://raw.githubusercontent.com/public-broadcasting/bbc-sounds-community-edition-for-sonos/main/img/music_service_list.jpg" alt="About My System" width="236" height="483">

<a href="https://support.sonos.com/article/add-a-music-service-to-sonos">Add</a> **BBC Sounds (Community Edition)** as a usual <a href="https://support.sonos.com/article/add-a-music-service-to-sonos">music service</a> to your system.

---

## Frequently Asked Questions

**I am located in the UK. Do I get any benefits from using BBC Sounds (Community Edition)?**

- The official <a href="(https://support.sonos.com/services/bbc-sounds">BBC Sounds</a> integration offers significantly more content and also transmits more information to the Sonos controller about the current program or currently playing tracks. Use your advantage and use the official BBC Sounds integration to fully utilize the offering.

**Does BBC Sounds (Community Edition) work with voice services like Amazon Alexa, Google Assistant or Sonos Voice?**

- BBC Sounds (Community Edition) has no association with Sonos, so it must be integrated through the <a href="https://developer.sonos.com/build/content-service-get-started/test-your-content-service/#Test-your-service-on-Sonos-with-Custom-SD">custom service descriptor page (CustomSD)</a>. This makes the integration self-contained and does not use any cloud-based services from Sonos. As there is no partnership, features like Voice Services cannot be integrated.
  
  The development of an Amazon Skills or Google Action is not planned.

**The BBC provides MPEG DASH streams. Can these also be added to BBC Sounds (Community Edition)?**

- This option has already been explored, but it was not possible to get it running on Sonos.

**There are several radio stations missing in BBC Sounds (Community Edition). Can the missing ones be added?**

- BBC Sounds (Community Edition) covers all BBC radio stations that belong to the BBC World Service. The missing radio stations are not available outside the UK.

  To test whether there is an error, you can visit the following page and select the desired radio station: https://www.bbc.co.uk/sounds/stations

  If you see the banner "*This content is not available in your location."* and you are outside the UK, everything is as expected. If not, please report the error through this <a href="https://github.com/public-broadcasting/bbc-sounds-community-edition-for-sonos/issues/new">link</a>.

**Can you assign a service logo to the BBC Sounds (Community Edition) integration?**

- This option is not available for custom integrations.

**I have found a bug or there is a problem with BBC Sounds (Community Edition), who do I contact?**

- If you have found an error, please report it through this <a href="https://github.com/public-broadcasting/bbc-sounds-community-edition-for-sonos/issues/new">link</a>. Please **do not** contact the BBC and/or Sonos support. They will not be able to help you in any case.

---

This project is not affiliated with the <a href="https://www.bbc.co.uk/sounds">BBC Sounds</a> or <a href="https://www.sonos.com/">Sonos</a>.

All mentioned trademarks are the property of their respective owners.
