# Chaospager Infos

All official information about the Chaospager developed by Signalspielplatz

All about the hardware can be found [HERE](/Hardware.md)

# Blogpost from C3 Blog

## About the project

It all started as a spontanous idea for 38c3: We thought "Why not bring a POCSAG transmitter to congress? But without receivers, no one will be able to use the system - so why not create our own pager project?"

In an effort of building a first pager prototype in just two months (brainstorming phase to finished device), we succeeded our goal and gave a talk about our project and ideas. Besides reaching many interested creatures of you (the Chaos Community), we attracted the attention of CERT who showed interest in our devices. At EasterHegg22, we conducted our first experiments for this cooperation and clarified the requirements of CERT for our system.

Now, in collaboration with [CERT](https://mastodon.social/@c3cert@chaos.social) and [DL0TUH](https://mastodon.social/@DL0TUH), we introduce the new prototype featuring a custom HF frontend, complete redesign of the board, new firmware and additional features!

## Join Our Talk at 39c3!

If you are interested in our project, please join our talk on 28. Dec 2025 at 14:45 (UTC+1) in Saal 1. Here, we will talk about the exploration phase of the initial pager idea, where we are now, what the challenges were and what our next goals are. We will also talk about our custom infrastructure for POCSAG transmitters and the goals of connecting it to THOT (CERTs own dispatch software).

If you would like to obtain a general sense of what it takes to do such a project, if you are interested in how to define requirements when developing critical infrastructure, or if you would like to get an insight of our engineers perspective on the project (e.g. experimental design, hardware design, etc.), this talk is for you! Don’t worry: We designed the talk in a way so that it'll be easy to follow even if you have no prior experience in this field.

## Build, Think, Receive

Are you interested in pagers in general, do you own one, or would you like to test our system with other software solutions?

We operate our system on 439.9875MHz. We provide you the following RICS:

| RIC | Description |
|-----|-------------|
| 8 | Sender-ID (DL0TUH) |
| 1111 | Info |
| 1122 | Tests |
| 1142 | Eventinfos |
| 2504 | Date & Time (Skyper) |

Please note that we cannot guarantee anything during operation, as we also need to conduct tests for our project.

## Further updates until the congress

In the meantime until congress, make sure to follow us on Mastodon, were we will post regular updates of our project: [https://mastodon.social/@signalspielplatz](https://mastodon.social/@signalspielplatz)
