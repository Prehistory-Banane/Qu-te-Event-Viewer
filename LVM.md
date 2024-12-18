# Quête LVM

## Ajout d'un nouveau disque dur sur VBox
### Vérification avec la commande `lsblk`
![1](https://github.com/user-attachments/assets/a1cdb6be-3db0-4072-bd33-b58eeb5ef700)

## Création d'un nouveau Volume Physique (PV)
![2](https://github.com/user-attachments/assets/7a407f5a-090e-4055-a9bb-f294b387d623)

## Vérification avec la commande `pvs`
![3](https://github.com/user-attachments/assets/cbc9c912-c781-4b4e-809e-e02a2982139b)

## Ajout du PV au Volume Group (VG)
![4](https://github.com/user-attachments/assets/e91bc315-ccb7-4c99-8273-0e0b2e82f636)

## Vérification avec la commande `vgdisplay`
![5](https://github.com/user-attachments/assets/5245b191-549f-4aa1-b87a-90d4daf383f1)

## Vérification Volume Logique avec la commande `lvdisplay`
![6](https://github.com/user-attachments/assets/41cb8ae6-f6da-41a3-98d8-fd41dbbeda68)

## Création d'un snapshot
![7](https://github.com/user-attachments/assets/85af588b-704a-438f-a6ee-515ebd0a4947)

## Vérification Volume Logique avec la commande `lvdisplay`
![8](https://github.com/user-attachments/assets/0ae8e762-9169-48cb-8724-47d3528bdfff)

## Création du dossier `/home-snap` et montage du snapshot dans ce dossier
![9](https://github.com/user-attachments/assets/d2cf9c4f-fa86-440f-a211-8b475f51ba3a)

## Vérification avec la commande `lsblk`
![10](https://github.com/user-attachments/assets/6b677718-02de-440d-b4ce-0d0ed5a70675)

## Comparaison du contenu entre /home et /home-snap
![11](https://github.com/user-attachments/assets/1c0ee845-2333-4478-bf74-4ca41befe5c2)

## Démontage de `/home-snap` et destruction finale de `snappy` (paix à son âme)
![12](https://github.com/user-attachments/assets/e3d4809e-556c-42ef-a498-e51ecff145bc)

## Un dernier `lsblk` pour vérifier qu'on est bien revenu à la situation de départ
![13](https://github.com/user-attachments/assets/aa93691a-0dee-4947-bbca-c240495fff78)


