# Questions Fréquemment Posées

### Instructions / Discussions
* [Instructions Vidéo](https://www.youtube.com/watch?v=4XN02GkcHUM) (Un grand merci à [TheiTeckHq](https://www.youtube.com/channel/UC_DUzWMb8gZZnAbISQjmAfQ))
* [idownloadblog](http://www.idownloadblog.com/2015/12/29/snapdrop/)
* [thenextweb](http://thenextweb.com/insider/2015/12/27/snapdrop-is-a-handy-web-based-replacement-for-apples-fiddly-airdrop-file-transfer-tool/)
* [winboard](http://www.winboard.org/artikel-ratgeber/6253-dateien-vom-desktop-pc-mit-anderen-plattformen-teilen-mit-snapdrop.html)
* [免費資源網路社群](https://free.com.tw/snapdrop/)
* [Hackernews](https://news.ycombinator.com/front?day=2020-12-24)
* [Reddit](https://www.reddit.com/r/Android/comments/et4qny/snapdrop_is_a_free_open_source_cross_platform/)
* [Producthunt](https://www.producthunt.com/posts/snapdrop)

### Aide ! Je ne peux pas installer l'application web progressive (PWA) !
Si vous utilisez un navigateur basé sur Chromium (Chrome, Edge, Brave, etc.), vous pouvez facilement installer Snapdrop en tant que PWA sur votre ordinateur de bureau en cliquant sur le bouton d'installation en haut à droite lorsque vous êtes sur [snapdrop.net](https://snapdrop.net) (voir ci-dessous).
<img src="pwa-install.png">

### Qu'en est-il de la connexion ? S'agit-il d'une connexion pair à pair (P2P) directement d'un appareil à un autre, ou y a-t-il un serveur tiers impliqué ?
Snapdrop utilise une connexion P2P si WebRTC est pris en charge par le navigateur. WebRTC nécessite un serveur de signalisation, mais il est uniquement utilisé pour établir une connexion et n'intervient pas dans le transfert de fichiers.

### Qu'en est-il de la confidentialité ? Les fichiers seront-ils enregistrés sur des serveurs tiers ?
Aucun de vos fichiers n'est jamais envoyé à un serveur tiers. Les fichiers sont envoyés uniquement entre pairs. Snapdrop n'utilise même pas de base de données. Si vous êtes curieux, vous pouvez consulter [le code du serveur](https://github.com/RobinLinus/snapdrop/blob/master/server/). Même si Snapdrop pouvait voir les fichiers en cours de transfert, WebRTC chiffre les fichiers en transit, de sorte que le serveur serait incapable de les lire.

### Qu'en est-il de la sécurité ? Mes fichiers sont-ils chiffrés lorsqu'ils sont envoyés entre les ordinateurs ?
Oui. Vos fichiers sont envoyés à l'aide de WebRTC, qui les chiffre en transit.

### Pourquoi n'implémentez-vous pas la fonctionnalité xyz ?
Snapdrop est une étude sur la simplicité radicale. L'interface utilisateur est incroyablement simple. Les fonctionnalités sont choisies très soigneusement car la complexité croît de manière quadratique, car chaque fonctionnalité interfère potentiellement avec toutes les autres. Nous nous concentrons très étroitement sur un seul cas d'utilisation : le transfert instantané de fichiers.
Nous n'essayons pas d'optimiser pour certains cas particuliers. Nous optimisons le flux de travail de l'utilisateur moyen. Ne soyez pas triste si nous refusons votre demande de fonctionnalité au nom de la simplicité.

Si vous souhaitez en savoir plus sur la simplicité, vous pouvez lire [Insanely Simple: The Obsession that Drives Apple's Success](https://www.amazon.com/Insanely-Simple-Ken-Segall-audiobook/dp/B007Z9686O) ou [Thinking, Fast and Slow](https://www.amazon.com/Thinking-Fast-Slow-Daniel-Kahneman/dp/0374533555).

### Snapdrop est génial ! Comment puis-je le soutenir ?
* [Faites un don via PayPal pour aider à couvrir les coûts du serveur](https://www.paypal.com/donate/?hosted_button_id=FTP9DXUR7LA7Q)
* [Signalez des bugs, donnez des commentaires, soumettez des suggestions](https://github.com/RobinLinus/snapdrop/issues)
* Partagez Snapdrop sur vos réseaux sociaux.
* Corrigez des bugs et soumettez une demande de pull (pull request).
* Effectuez des analyses de sécurité et proposez des suggestions.

## Instances "Non officielles"
Voici une liste d'autres personnes hébergeant des instances non officielles de Snapdrop :

- https://snapdrop.k26.ch/
- https://snapdrop.9pfs.repl.co/
- https://filedrop.codext.de/
- https://s.hoothin.com/
- https://www.wulingate.com/
- https://snapdrop.fairysoft.net/
- https://airtransferer.web.app/

AVERTISSEMENT : NOUS NE SOMMES EN AUCUN CAS AFFILIÉS AUX PERSONNES QUI GÈRENT CES INSTANCES. NOUS NE LES CONNAISSONS PAS. NOUS NE POUVONS PAS VÉRIFIER LE CODE QU'ILS EXÉCUTENT !

## Applications Tierces
Voici une liste de certaines applications tierces pour Snapdrop :

1. [Application de bureau Snapdrop](https://github.com/alextwothousand/snapdrop-desktop) basée sur Electron. (Merci à [alextwothousand](https://github.com/alextwothousand/)).

2. [Application Android Snapdrop](https://github.com/fm-sys/snapdrop-android) qui vous permet également d'envoyer des fichiers directement à partir d'autres applications via l'action de partage.

3. [Application Flutter Snapdrop](https://github.com/congnguyendinh0/snapdrop_flutter)

4. [Application iOS Snapdrop](https://github.com/CDsigma/Snapdrop-iOS-App)

5. [Application Node Snapdrop (avec serveur complètement Node)](https://github.com/Bellisario/node-snapdrop)

6. [Extension VSCode SnapDrop](https://github.com/Yash-Garg/snapdrop-vsc)

7. N'hésitez pas à en créer une vous-même :)

[< Retour](/README.md)
