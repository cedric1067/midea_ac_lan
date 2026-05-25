# Midea AC LAN
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/hacs/integration)
[![Donate](https://img.shields.io/badge/donate-BuyMeCoffee-yellow.svg)](https://www.buymeacoffee.com/georgezhao2010)
[![Stable](https://img.shields.io/github/v/release/georgezhao2010/midea_ac_lan)](https://github.com/georgezhao2010/midea_ac_lan/releases/latest)

[English](README.md) | [简体中文](README_hans.md) | Français

Pilotez vos appareils Midea M-Smart en réseau local.

- Découverte et configuration automatique des appareils via l'interface de configuration de Home Assistant.
- Capteurs et interrupteurs supplémentaires.
- Synchronisation en temps réel de l'état de l'appareil grâce à une connexion TCP persistante.

Ce composant s'inspire du dépôt [@mac-zhou](https://github.com/mac-zhou/midea-msmart), qui propose des fonctionnalités similaires pour les climatiseurs Midea. Il inclut, à l'identique ou adaptées, des portions de code issues de ses excellents projets.

Merci également à [@NeoAcheron](https://github.com/NeoAcheron/midea-ac-py).

⭐ Si ce composant vous est utile, n'hésitez pas à lui mettre une étoile, c'est très encourageant.

***❗ Note : Home Assistant 2022.5 ou supérieur est requis pour cette intégration.***

# Marques prises en charge

![ariston](brands/ariston.png) ![beverly](brands/beverly.png) ![bugu](brands/bugu.png) ![carrier](brands/carrier.png)  ![colmo](brands/colmo.png) ![comfee](brands/comfee.png) ![electrolux](brands/electrolux.png) ![invertor](brands/invertor.png) ![littleswan](brands/littleswan.png) ![midea](brands/midea.png) ![netsu](brands/netsu.png) ![ProBreeze](brands/probreeze.png) ![rotenso](brands/rotenso.png) ![toshiba](brands/toshiba.png) ![vandelo](brands/vandelo.png) ![wahin](brands/wahin.png)

Et d'autres encore.

# Appareils pris en charge

| Type | Nom                                  | Documentation      |
|------|--------------------------------------|--------------------|
| 13   | Éclairage                            | [13.md](doc/13.md) |
| 26   | Bloc salle de bain                   | [26.md](doc/26.md) |
| 34   | Lave-vaisselle évier                 | [34.md](doc/34.md) |
| 40   | Ventilateur de plafond intégré       | [40.md](doc/40.md) |
| A1   | Déshumidificateur                    | [A1.md](doc/A1.md) |
| AC   | Climatiseur                          | [AC.md](doc/AC.md) |
| B0   | Four à micro-ondes                   | [B0.md](doc/B0.md) |
| B1   | Four électrique                      | [B1.md](doc/B1.md) |
| B3   | Stérilisateur de vaisselle           | [B3.md](doc/B3.md) |
| B4   | Grille-pain                          | [B4.md](doc/B4.md) |
| B6   | Hotte aspirante                      | [B6.md](doc/B6.md) |
| BF   | Four micro-ondes vapeur              | [BF.md](doc/BF.md) |
| C2   | WC connecté                          | [C2.md](doc/C2.md) |
| C3   | Contrôleur Wi-Fi pour pompe à chaleur| [C3.md](doc/C3.md) |
| CA   | Réfrigérateur                        | [CA.md](doc/CA.md) |
| CC   | Contrôleur Wi-Fi MDV                 | [CC.md](doc/CC.md) |
| CD   | Chauffe-eau thermodynamique          | [CD.md](doc/CD.md) |
| CE   | Centrale d'air neuf                  | [CE.md](doc/CE.md) |
| CF   | Pompe à chaleur                      | [CF.md](doc/CF.md) |
| DA   | Lave-linge à chargement par le dessus| [DA.md](doc/DA.md) |
| DB   | Lave-linge à chargement frontal      | [DB.md](doc/DB.md) |
| DC   | Sèche-linge                          | [DC.md](doc/DC.md) |
| E1   | Lave-vaisselle                       | [E1.md](doc/E1.md) |
| E2   | Chauffe-eau électrique               | [E2.md](doc/E2.md) |
| E3   | Chauffe-eau gaz                      | [E3.md](doc/E3.md) |
| E6   | Plaque de cuisson gaz                | [E6.md](doc/E6.md) |
| E8   | Mijoteuse électrique                 | [E8.md](doc/E8.md) |
| EA   | Cuiseur à riz électrique             | [EA.md](doc/EA.md) |
| EC   | Autocuiseur électrique               | [EC.md](doc/EC.md) |
| ED   | Fontaine à eau                       | [ED.md](doc/ED.md) |
| FA   | Ventilateur                          | [FA.md](doc/FA.md) |
| FB   | Radiateur électrique                 | [FB.md](doc/FB.md) |
| FC   | Purificateur d'air                   | [FC.md](doc/FC.md) |
| FD   | Humidificateur                       | [FD.md](doc/FD.md) |

# Installation
Cherchez « Midea AC LAN » dans HACS et installez-le, ou copiez manuellement tous les fichiers du dossier `custom_components/midea_ac_lan` depuis la [dernière version](https://github.com/georgezhao2010/midea_ac_lan/releases/latest) vers `/custom_components/midea_ac_lan` dans Home Assistant.

Redémarrez Home Assistant.

# Ajouter un appareil
***❗ Note : commencez par fixer une adresse IP statique pour votre appareil dans votre routeur, afin d'éviter que son IP ne change après la configuration.***

Une fois l'installation effectuée, recherchez et ajoutez le composant « Midea AC LAN » dans la page des intégrations de Home Assistant.

Ou cliquez sur [![Configuration](https://my.home-assistant.io/badges/config_flow_start.svg)](https://my.home-assistant.io/redirect/config_flow_start?domain=midea_ac_lan)

***❗ Note : pendant la configuration, il pourra vous être demandé de saisir votre compte et mot de passe Midea. C'est nécessaire pour récupérer les informations des appareils (Token et Clé) depuis le serveur cloud Midea. Une fois tous les appareils configurés, vous pouvez supprimer la configuration du compte Midea sans impact sur leur fonctionnement.***

Après avoir configuré le compte, cliquez à nouveau sur « AJOUTER UN APPAREIL » pour ajouter un nouvel appareil. Répétez l'opération pour ajouter plusieurs appareils.

## Découverte automatique
Avec cette option, le composant peut détecter et lister automatiquement les appareils Midea M-Smart présents sur le réseau ou à une adresse IP donnée ; sélectionnez-en un pour l'ajouter.

Vous pouvez aussi utiliser une adresse de diffusion pour cibler un réseau précis, par exemple `192.168.1.255`.

***❗ Note : la découverte automatique nécessite que vos appareils et votre Home Assistant soient sur le même sous-réseau. À défaut, les appareils risquent de ne pas être détectés. Vérifiez ce point par vous-même.***

## Configuration manuelle
Si vous disposez déjà des informations suivantes, vous pouvez ajouter l'appareil manuellement.
- Code de l'appareil
- Type d'appareil (parmi [Appareils pris en charge](README_fr.md#appareils-pris-en-charge))
- Adresse IP
- Port (6444 par défaut)
- Version du protocole
- Token
- Clé

## Lister uniquement les appareils
Avec cette option, vous pouvez lister tous les appareils Midea M-Smart détectables sur le réseau, avec leurs identifiants, types, numéros de série et autres informations.

***❗ Note : pour diverses raisons, certains appareils pris en charge peuvent ne pas apparaître ici.***

# Configurer

La configuration est accessible via `Paramètres → Appareils et services → Midea AC LAN → Appareils → CONFIGURER`.
Vous pouvez y redéfinir l'adresse IP en cas de changement.
Vous pouvez également ajouter des capteurs et interrupteurs supplémentaires ou personnaliser votre appareil.

## Adresse IP
Définit l'adresse IP de l'appareil. À réinitialiser si l'IP change.

## Intervalle de rafraîchissement
Définit l'intervalle (en secondes) pour rafraîchir activement l'état d'un appareil (30 par défaut, 0 désactive le rafraîchissement actif).
La plupart du temps, la mise à jour d'état des appareils Midea repose sur leurs notifications spontanées : dans ce cas la mise à jour fonctionne même avec un intervalle à « 0 ». Le composant interroge également l'appareil à intervalle régulier (30 s par défaut). Certains appareils n'émettent pas de notification à chaque changement d'état, la synchronisation dans HA est alors plus lente. Si la rapidité de synchronisation vous importe, réduisez l'intervalle.

***❗ Note : un intervalle plus court signifie potentiellement une consommation électrique plus élevée.***

## Capteurs et interrupteurs supplémentaires
Après configuration, une entité principale (par exemple `climate`) est créée. Pour exposer les autres attributs sous forme de capteurs ou d'interrupteurs supplémentaires, cliquez sur CONFIGURER dans la carte d'intégration Midea AC LAN (selon le support de votre appareil).

## Personnaliser
Certains types d'appareils ont leurs propres options de configuration ; si votre appareil ne fonctionne pas correctement, vous devrez peut-être les personnaliser. Référez-vous à la documentation de l'appareil pour les détails.

Le format des personnalisations doit être du JSON.

Si plusieurs options doivent être configurées, l'ensemble doit respecter le format JSON.

Exemple :
```json
{"refresh_interval": 15, "fan_speed":  100}
```

# Débogage

Activez les logs de debug dans `configuration.yaml` :
```yaml
logger:
  default: warn
  logs:
    custom_components.midea_ac_lan: debug
```

# Soutenir le projet

Si vous aimez cette intégration, vous pouvez soutenir son auteur en lui offrant un café.

[![Buy me a coffee](https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png)](https://www.buymeacoffee.com/georgezhao2010)
