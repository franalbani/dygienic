# dygienic

Higiene digital básica

## Contraseñas

* Una passphrases maestra generadas con [Diceware](https://theworld.com/~reinhold/diceware_espanol/DW-Espanol-1.txt) para la base de datos de KeePassXC.
* Para cada servicio una contraseña:
    * distinta
    * larga
    * aleatoria
    * almacenada en KeePassXC

https://xkcd.com/936/

* Cuidado con Lastpass: https://blog.lastpass.com/2022/12/notice-of-recent-security-incident/

## Filesystem

* LUKS con passphrase generada por diceware.

### Tarjeta SD encriptada

#### Creación
* Crear partición tipo Linux (83) en `/dev/mmcblk0p1`
* `cryptsetup luksFormat --type luks2 /dev/mmcblk0p1`
* Ingresar passphrase.
* `cryptsetup open /dev/mmcblk0p1 sdcrypt`
* `mkfs.ext4 /dev/mapper/sdcrypt`
* `cryptsetup close sdcrypt`

#### Uso
* `cryptsetup open /dev/mmcblk0p1 sdcrypt`
* `mount /dev/mapper/sdcrypt /mnt/`
* `cryptsetup close sdcrypt`

## Mail

* Proton Mail

## Videollamada

* jitsi

## Mensajería

* Signal

## Toma de notas

* [Standar Notes](https://standardnotes.org)

## Navegar sin que nuestro proveedor de Internet pueda espiarnos

* OpenVPN
* ProtonVPN
