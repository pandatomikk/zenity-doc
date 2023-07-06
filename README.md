# zenity-doc
personal doc for zenity

Exporter les sortie en string
```
bash
var=$(zenity --error --title "Wrong password" --text="Mauvais mot de passe)

```

### Redimensionnement de fenêtres

--width=000 --height=000 --no-wrap

```
bash
zenity --error --title "Wrong password" --width=100 --height=100 --no-wrap --text="Mauvais mot de passe"
```
### ajout de boutton

--extra-button=""


```
bash
zenity --info --title=”Motor Control” --text “Motor Action control” --ok-label=”Start” --extra-button=”Stop”--extra-button=”Forword” --extra-button=”Backword”
```
Les boutons par défaut retourne 0 pour annuler et 1 pour Ok 


### prise du mot de passe et verificaiton si le mot de passe root est bon
```
password=$(zenity --title "Password" --text="Entrez votre mot de passe root" --password)
chmod +x *.sh
chkroot=$(echo $password | sudo -S whoami)
if [ "$password" = "" ]; then
exit
elif [ "$chkroot" != "root" ]; then
zenity --error --title "Wrong password" --text="Mauvais mot de passe"
exit
fi
```
