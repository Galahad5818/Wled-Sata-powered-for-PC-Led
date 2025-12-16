# Wled-Sata-powered-for-PC-Led
> Carte électronique DIY permettant d’alimenter et de piloter des LEDs RGB (WS281x / ARGB PC)  
> via un **ESP8266 + WLED**, directement depuis l’alimentation **SATA d’un PC**.

PCB DIY WLED Sata powered           |  Solarized Ocean
:-------------------------:|:-------------------------:
 ![IMG_20251211_190525](https://github.com/user-attachments/assets/ce8f3694-5dff-402e-922a-71ee93638b5a) |  ![IMG_20251214_222030](https://github.com/user-attachments/assets/2433ffcc-880a-44a4-bc34-8d50b4247145)


## 📌 Présentation

Ce projet est une **carte électronique custom** conçue pour intégrer proprement **WLED** dans un PC :

- ⚡ Alimentation directe via **connecteur SATA**
- 🧠 Microcontrôleur : **ESP8266**
- 🌈 Contrôle de LEDs RGB adressables
- 🔌 Connectique pensée pour le PC et les rubans LED

L’objectif est d’obtenir une solution **propre, intégrée et open-source**, inspirée des contrôleurs RGB commerciaux, mais en version **DIY**.

👉 Ce projet vise à **imiter fonctionnellement** la carte suivante (version commerciale) :  
https://fr.aliexpress.com/item/1005008226291294.html

---

## ✨ Fonctionnalités

- Alimentation via **SATA PC**
- Compatible **WLED**
- **8 sorties LED indépendantes**, chacune avec son GPIO dédié :
  - **4 × JST** (rubans LED type WS281x)
  - **4 × ARGB PC** (compatibles Asus Aura, MSI Mystic Light, etc.)
- Connecteurs ARGB au **pas 1.27 mm**
- Répartition intelligente de l’alimentation :
  - 1 ligne +5V pour les sorties JST
  - 1 ligne +5V dédiée à l’ESP8266
  - 1 ligne +5V pour les autres connecteurs LED
- Synchronisation RGB avec le PC via **SignalRGB**

---

## 🧠 Architecture & logique

- L’ESP8266 est alimenté directement par le SATA
- Chaque sortie LED possède :
  - Son propre GPIO
  - Son alimentation dédiée
- Les **GPIO utilisés sont indiqués directement sur le PCB**, à côté de chaque connecteur
- Le firmware **WLED** permet :
  - Le contrôle réseau
  - L’intégration SignalRGB
  - La gestion multi-canaux

---

## 🔧 Assemblage

### Matériel nécessaire

- Un **fer à souder**
- Les composants listés dans le dossier `Composent/`
- Un ESP8266 compatible

### Logiciel

- Installation de **WLED** sur l’ESP8266  
  👉 De nombreux tutoriels existent déjà (non spécifiques à cette carte)
- Aucune configuration spéciale côté firmware :
  - Les GPIO sont déjà définis sur le PCB
- Une fois WLED connecté au réseau :
  - **SignalRGB détecte automatiquement WLED**
  - L’ajout du composant est guidé dans le logiciel

---

## 🧪 Matériel utilisé

La liste complète des composants se trouve dans le dossier **`Composent/`**.

- Microcontrôleur : **ESP8266**
- Alimentation : **SATA PC**
- PCB : custom
- Connecteurs :
  - JST (WS281x)
  - ARGB PC (1.27 mm)

---

## 📸 Photos

*(Photos de la carte, du montage et de l’utilisation dans un PC à ajouter ici)*

---

## ⚠️ Points d’amélioration & défauts

### Largeur des pistes d’alimentation

- Fonctionne correctement dans mon usage personnel
- ⚠️ **Si vous prévoyez beaucoup de LEDs** :
  - Augmenter la largeur des pistes +5V / GND
  - Multiplier les vias d’alimentation
- Recommandation valable pour les connecteurs LED  
  *(pas nécessaire pour l’ESP)*

### Footprint du connecteur SATA

- Décalage constaté entre :
  - Les dimensions annoncées (AliExpress)
  - Le connecteur réel
- Conséquence :
  - Une patte de fixation ne tombait pas en face
- Solution appliquée :
  - Suppression d’une patte latérale
  - Le connecteur reste parfaitement fixé grâce aux **15 pins SATA soudées**

---

## 📝 Notes importantes

- Cette carte **fonctionne dans mon usage personnel**
- Je partage **une idée et une réalisation DIY**
- ⚠️ **Je ne suis pas responsable de l’utilisation que vous en ferez**
- Bien dimensionner l’alimentation selon votre nombre de LEDs

---

## 📜 Licence

Projet **DIY / open-source** :

- Utilisation **personnelle uniquement**
- ❌ Usage commercial interdit
- Libre de modification et d’adaptation à titre personnel
