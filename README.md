# Anonymisation BURP

## Introduction 

Ci-joint quelques customisations pour personnaliser BURP, via les fichiers "user" et "projet". L'objectif est de restreindre certains actions automatiques de BURP induites par une configuration par défaut.

## Sommaire

- Intercept Proxy
- Exclusions Proxy
- Sauvegardes Automatiques 
- Exclude Colaborator
- Updates
- Reload extensions
- Disabled extensions

## Intercept Proxy

BURP > Tools > Proxy

- Response interception rules : on
- Default Proxy interception state : off

## Exclusions Proxy

- cf. https://gist.githubusercontent.com/fyxme/8e8677194313593a230e42f16428cd26/raw/ac36c89122f66b109e9ddf00b1993b6805d2cd5a/burp-target-scope-options.json
- cf. https://github.com/SeanWrightSec/proxy-bypass-list/blob/master/foxyproxy-patterns.json
- cf. https://gist.github.com/todmephis/d25ee066574545f32bd6ebb70a9228f5

BURP > Settings > Project > Scope

Exclude from scope : 
'''sh
https://portswigger.net
*.oastify.com
*.mozilla.*
*.firefox.*
*.microsoft.*
*.windows.*
...
'''

## Sauvegardes Automatiques 

BURP > Settings > Projet > Automatic backup

- Automatically back up the project every : 60 minutes
- Show progress dialog during backups : off

## Exclude Colaborator

BURP > Settings > Project > Collaborator

- Burp Collaborator server : off

## Updates

BURP > Settings > Suite > Updates

- Updates : off
- Performance feedback : off

BURP > Settings > Suite > Startup behavior

- Automatated tasks on startup : on
- Maximum Java memory usage : system

## Reload extensions

BURP > Settings > Extensions > Startup behavior

- Automatically reload extensions on startup : off
- Automatically reload installed BApps on startup : off

## Disabled extensions

BURP > Startup

- Disable extensions : off

# Fichiers de configuration

Fichiers par défaut dans $HOME/.BurpSuite :
- Projet : WorkspaceConfigPro.json
- User : UserConfigPro.json

Charger les fichiers joints pour remplacer les fichiers par défaut. Le remplacement avant démarrage de BURP évite certains effets de bord natifs. Sinon un chargement post démarrage est toujours possible.