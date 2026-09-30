# NPM-config
Script för att konfigurera Nginx Proxy Manager via API.

## Kräver:
  1. Fil med lösenord till NPM-server.
  2. Fil med domäner, ipadresser och portar som ska läggas in efter följande format "DOMÄN IP PORT". Kräver en tom rad på slutet.

## Användning:

```
bash NPM_conf.sh -t http://192.168.0.202:81 -u admin@admin.com -p secret -f hosts.txt
```

| Flagga | Beskrivning |
|--------|-------------|
| `-t` | Adress till NPM servern, inklusive port 81 |
| `-u` | E-postadress för inloggning i NPM |
| `-p` | Sökväg till filen med lösenordet |
| `-f` | Sökväg till filen med domäner |

Alla flaggor måste anges. Lösenordsfilen ska bara innehålla lösenordet på första raden. Scriptet har ingen felhantering. Om en domän redan finns i NPM misslyckas det anropet, men scriptet fortsätter med nästa rad.



## Exempel på domänfil:
```
adguard.hemma.lan 192.168.0.25 8080
jellyfin.hemma.lan 192.168.0.50 8096
proxmox.hemma.lan 192.168.0.10 8006

```
**OBS:** Filen måste sluta med en tom rad efter sista raden, annars läses den inte in.
