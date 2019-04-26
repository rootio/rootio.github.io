### Welcome to the RootIO Project.
RootIO Radio stations are tiny FM radio stations that require little investment, maintenance, or contribution from the community, yet at the same time offer more and better modes of interaction than traditional stations. They are backed by a cloud service that connects the station with telephony and the Internet, allowing many new forms of interaction and information flows. After a few days of installation and training, stations can start to facilitate new economic opportunities, new opportunities for expression and deliberation, and provide information across, into, and out of the community they serve. Listeners just use the same FM radios they already use; if they have a feature (non-smart) phone they can interact with the station in a variety of ways. More general information can be found at our [public site](http://rootio.org).

### Our Code of Conduct
[Code_Of_Conduct](https://github.com/rootio/rootio.github.io/blob/master/CODE_OF_CONDUCT.md)

### Who is RootIO
RootIO is a team of creative technologists from around the world who saw the continued importance of FM in much of the world, and wanted to make sure it received at least a fraction of the attention that apps, IOT, and the Kardashians get. We imagined Community Radio as a Service (CRaaS), and went about scaling a radio station down to the smallest size as we could imagine, a size which would allow a neighborhood or village to have a station without having to pour resources into it. We've been facilitating four stations in rural Uganda with reasonable success. @csik and @judelove founded the project.

### How does it work?
The stations themselves are comprised of an android phone running our app, solar power, a radio tower, and an FM transmitter. There is no studio. This is backed up by 1) community and 2) a cloud service. The cloud service can grab podcasts and audio from around the Internet, push content to the stations via data, count SMS votes, etc. But it also is hooked into a telephony switch, which allows it to make or recieve calls. Together, this means that stations in rural areas with only GSM can still receive up-to-date audio content, emergency reports, or talk shows with callers.

*A farmer who has lost their cow can call in an advertisement to play on the air.
*An agricultural extension officer can communicate with all the farmers in their community.
*Local high-school football games are announced live via phone from the sidelines.
*Stations generate money for their local operations, making themselves sustainable.
*The cost of participation is offset from local and cloud revenue, making it much more easy for the majority of the population to participate.

### What's all this code?
The project is divided into three parts:
+ _rootio_handset_ 
This is the android code that runs on the station's phone. It is currently factored for a Samsung Pocket Galaxy, though we are probably upgrading to a Duos family phone in the near future. To keep development costs down we are assuming each station has one of these phones, chosen as some of the cheapest in the Subsaharan Africa market. This is a complex app that touches many, many of the subsystems on the phone, from telephony to power, data to storage. The station phones can synchronize their schedule with the cloud and exchange their status through an API with the web service. Built in Java.
 
+ _rootio_web_
This is the web service that allows management of scheduling a station, viewing programs, etc. Station managers might look at this every once in a while, but it is essentially an admin interface to the cloud system. It shows real-time status of the phone network as well. Built in python on Flask.

+ _station_telephony_
This is the telephony backend, where a software daemon lives for each station processing programming an interactions as a state machine, and also exchanges information with the telephony switch and possibly also telcos. Built in python on Freeswitch, communicating to the web service through ZMQ signals.

We are adding overall project documentation at on the wiki for this [page] (https://github.com/rootio/rootio.github.io/wiki)

### Contribute
Please email info@rootio.org if you have any questions.

