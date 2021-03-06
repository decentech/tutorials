# What Is Riot?
* **decentralised** - based on [Matrix](http://matrix.org/#about)
* **open source** - [Apache 2.0 License](https://choosealicense.com/licenses/apache-2.0/)
* **federated**
* end to end (E2E) **encrypted** - [still in BETA labs](https://medium.com/@RiotChat/exciting-new-riot-release-get-ready-for-chatting-securely-acc93ecfe0a)
* **interoperable**
  * Linux
  * Windows
  * Mac
  * Android
  * Fdroid
  * iOS
  * Windows Phone
  * Webapp
* **group chat**
* **voip**
* **video**
* **private or public**
* **integrations**
  * IRC
  * Slack
  * Github
  * Gitter
  * Jira
  * Travis CI
  * Atom/RSS Feeds
  * Guggy
  * OFTC
  * Snoonet
  * Twitter
  * Giphy
  * Google Image Search
* **Optional 3rd party ID**
  * email
  * phone
  * Facebook
* **no single point of failure**
* **no limits** on features, group size, or usage of public rooms
* use the same identity across devices

# What's So Innovative About It?
Originally launching the BETA at [Decentralized Web Summit](https://archive.org/details/DWebSummit2016_Lightning_Talks_Session_B) in June 2016, as Vector, Riot allows you to own your own data. Of course it's decentralised. It's your bridge across a sea of communication apps.

Unlike Signal, Riot is not tied to your telephone number or the Android's 'Google Play' framework.

# What's the Riot Stance on Privacy?
To quote their blog:

"We stand behind the idea that all of us should have the right to control our online data and that sharing this data is a choice. We will not contribute to the ever growing belief that simply because something is free that by default you should give up your right to privacy.!

"Vector is a fully decentralized system, allowing anyone to run their own server in order to keep control over their data, and with the ability to provide an end-to-end encrypted service coming in our next release. Privacy and data ownership is critical to us." [Source](https://medium.com/@RiotChat/say-hello-to-vector-2d33b23a787)

Signal requires SMS confirmation which can be intercepted in authoritarian states. Riot does not require this. 

Riot's [Privacy Policy](https://riot.im/privacy)

# Coming Soon
* paid hosting support
* more integrations - Basecamp, Invision, Zeplin
* message editing
* reactions
* threads
* sharing of public encryption keys
* stable release v1.0

# Setup Riot
**Riot is still in beta. It's not yet rock solid. There might be some occasionally odd behaviour. Most importantly the encryption is still in labs. Proceed with caution.**

There are a clearly a big number of ways to install Riot. Installing on a phone is rather standard when it comes to apps. Being a beta, however, it's a little more testing. The documentation it's rather outstanding, but I am sharing my own version as content for decen.tech, and also for those that might like my alternative way of describing the task.

I use Linux as my everyday operating system. If you use Debian, your in luck, as there's a DEB file just for you. I use Arch Linux though. And as an added measure of personal security I have been guided to fully trust Arch User Repository (AUR). So far I've been unable to install a couple of apps as the process can be quite complex when you factor in dependancies. Riot was pretty easy in retrospect. So much so I tried installing in THREE different ways. As a self hosted webapp, as a self hosted development environment webapp, and as a desktop app. I nearly had an alternative version of the desktop app, but I don't understand Electron enough. I don't like to pretend I know something, but while edit this in the future once of I've grasped Electron. Here's how I went about it on Arch Linux using [this source](https://github.com/vector-im/riot-web).

# Riot Desktop App Version 1
This installation assumes you have an active version of NodeJS. Personally, I've preferred this installed via [NVM](https://github.com/creationix/nvm). Nativefier will install a native stand-alone Electron wrapper around the web app. 

1. `sudo npm install nativefier -g`
2. `cd your/preferred/path/`
3. `nativefier https://riot.im/app/`
4. `./riot-*your-native-env*`

# Riot Self Hosted Web App
This installation again relies on NodeJS.

2. `cd your/preferred/path/`
3. `git clone https://github.com/vector-im/riot-web.git`
4. `cd riot-web/`
5. `npm install`
6. `npm start`
7. In your web browser address bar navigate to `http://127.0.0.1:8080/` or `http://localhost:8080`
8. Periodically you should **update this installation** via:
9. Navigate to the root `riot-web/` directory
10. `git pull`
11. `npm install`
12. `npm start`

# Riot Self Hosted Development Environment Web App

1. **Clone and build matrix-js-sdk**
2. `git clone https://github.com/matrix-org/matrix-js-sdk.git`
3. `pushd matrix-js-sdk`
4. `git checkout develop`
5. `npm install`
6. `npm install source-map-loader`
7. `popd`
8. **Clone and build matrix-react-sdk**
9. `git clone https://github.com/matrix-org/matrix-react-sdk.git`
10. `pushd matrix-js-sdk`
11. `git checkout develop`
12. `npm install`
13. `rm -r node_modules/matrix-js-sdk; ln -s ../../matrix-js-sdk node_modules/`
14. `pushd`
15. **Clone, build and start Riot**
16. `git clone https://github.com/vector-im/riot-web.git` 
17. `cd riot-web`
18. `git checkout develop`
19. `npm install`
20. `rm -r node_modules/matrix-js-sdk; ln -s ../../matrix-js-sdk node_modules/`
21. `rm -r node_modules/matrix-react-sdk; ln -s ../../matrix-react-sdk node_modules/`
22. `npm start`
23. In your browser address bar navigate to `http://127.0.0.1:8080/` or `http://localhost:8080/`
