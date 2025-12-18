# Wled-Sata-powered-for-PC-Led
> Carte électronique DIY permettant d’alimenter et de piloter des LEDs RGB (WS281x / ARGB PC)  
> via un **ESP8266 + WLED**, directement depuis l’alimentation **SATA d’un PC**.

PCB DIY WLED Sata powered           |  Photo de l'utilisation dans mon ordinateur
:-------------------------:|:-------------------------:
 ![IMG_20251211_190525](https://github.com/user-attachments/assets/ce8f3694-5dff-402e-922a-71ee93638b5a) |  ![IMG_20251214_222030](https://github.com/user-attachments/assets/2433ffcc-880a-44a4-bc34-8d50b4247145)


## Présentation

Ce projet est une **carte électronique custom** conçue pour intégrer proprement **WLED** dans un PC :

- Alimentation directe via **connecteur SATA**
- Microcontrôleur : **ESP8266**
- Contrôle de LEDs RGB adressables
- 🔌 Connectique pensée pour le PC et les rubans LED

L’objectif est d’obtenir une solution **propre, intégrée et open-source**, inspirée des contrôleurs RGB commerciaux, mais en version **DIY**.

Ce projet vise à **imiter fonctionnellement** les cartes Nollie comme la carte suivante (version commerciale) :  
https://fr.aliexpress.com/item/1005008226291294.html

---

## Fonctionnalités

- Alimentation via **Alimentation SATA de PC**
- Compatible **WLED**
- **8 sorties LED adressable indépendantes**, chacune avec son GPIO dédié (Les GPIO utilisés sont indiqués directement sur le PCB, à côté de chaque connecteur) :
  - **4 × JST** (connecteur de rubans LED type WS281x)
  - **4 × ARGB PC** (compatibles Asus Aura, MSI Mystic Light, etc.) 3 pins au **pas 1.27 mm**
- Répartition intelligente de l’alimentation SATA:
  - 1 ligne +5V pour les sorties JST
  - 1 ligne +5V dédiée à l’ESP8266
  - 1 ligne +5V pour les autres connecteurs LED
- Grande compatibilité grâce à WLED : Synchronisation RGB possible avec le PC via **SignalRGB**, ou **HomeAssistant**, ...

---

## 🔧 Assemblage

### Matériel nécessaire

- Un **fer à souder**
- Les composants listés dans le dossier `Composant/`
- Un ESP8266 compatible

### Logiciel

- Installation de **WLED** sur l’ESP8266  
  De nombreux tutoriels existent déjà (non spécifiques à cette carte)
- Aucune configuration spéciale côté firmware :
- Une fois WLED connecté au réseau :
  - **SignalRGB détecte automatiquement WLED**
  - L’ajout du composant est guidé dans le logiciel

---

## Photos
![IMG_20251211_190525](https://github.com/user-attachments/assets/23ba78ee-fea0-4131-bf57-96efdfada356)
![IMG_20251211_190403](https://github.com/user-attachments/assets/26f91ee7-90ff-48fc-bc4f-b972d7f4698c)
![IMG_20251211_190451](https://github.com/user-attachments/assets/8afacb06-c0b2-4ee4-acc3-655075d85444)
<img width="2160" height="842" alt="3D_PCB_Sata_To_Wled" src="https://github.com/user-attachments/assets/25d1c298-cbe6-4cd0-bf80-f61cf5db0862" />

---

## ⚠️ Points d’amélioration & défauts

### Largeur des pistes d’alimentation

- Fonctionne correctement dans mon usage personnel
- ⚠️ **Si vous prévoyez beaucoup de LEDs** :
  - Augmenter la largeur des pistes +5V / GND
  - Ou, multiplier les vias d’alimentation
- Recommandation valable pour les connecteurs LED *(pas nécessaire pour l’ESP)*

### Footprint du connecteur SATA

- Décalage constaté entre :
  - Les dimensions annoncées (AliExpress)
  - Le connecteur réel
- Conséquence :
  - Une patte de fixation ne tombait pas en face
- Solution appliquée :
  - Suppression d’une patte latérale
  - Le connecteur reste parfaitement fixé grâce aux **15 pins SATA soudées**

Photo 1  |  Photo 2
:-------------------------:|:-------------------------:
![IMG_20251114_234242](https://github.com/user-attachments/assets/cb6f7d32-6ac5-452e-8f6d-dbddab31047a) | ![IMG_20251114_234229](https://github.com/user-attachments/assets/8b426258-687a-4764-bf41-adaa466f1e08)

---

## Notes importantes
> [!IMPORTANT]
> - Cette carte **fonctionne dans mon usage personnel**
> - Je partage **une idée et une réalisation DIY**
> - **Je ne suis pas responsable de l’utilisation que vous en ferez**
> - Bien dimensionner l’alimentation selon votre nombre de LEDs

---

## Licence

Projet **DIY / open-source** :

- Utilisation **personnelle uniquement**
- Usage commercial interdit
- Libre de modification et d’adaptation à titre personnel
