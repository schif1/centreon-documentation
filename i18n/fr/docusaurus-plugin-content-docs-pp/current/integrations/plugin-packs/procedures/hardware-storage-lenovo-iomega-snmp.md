---
id: hardware-storage-lenovo-iomega-snmp
title: Lenovo Iomega
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

	
## Contenu du Pack de supervision

### Objets supervisés

Le Pack Lenovo Iomega collecte les données pour:
* Cpu
* Disks
* Hardware
* Interfaces
* Memory

### Règles de découvertes

<Tabs groupId="sync">
<TabItem value="Services" label="Services">

| Nom de la règle                               | Description                                                                                  |
| :-------------------------------------------- | :------------------------------------------------------------------------------------------- |
| HW-Storage-Lenovo-Iomega-SNMP-Disk-Name       | Découvre les partitions et supervise l'utilisation disque                                    |
| HW-Storage-Lenovo-Iomega-SNMP-Interface-Name  | Découvre les interfaces réseaux et supervise le statut et l'utilisation de la bande passante |

</TabItem>
</Tabs>

### Métriques collectées 

<Tabs groupId="sync">
<TabItem value="Cpu" label="Cpu">

| Metric name                      | Description           | Unit |
| :------------------------------- | :-------------------- |:---- |
| cpu.utilization.percentage       | CPU utilization.      | %    |
| core.cpu.utilization.percentage  | CPU Core utilization. | %    |

</TabItem>
<TabItem value="Disks" label="Disks">

| Metric name                                  | Description                     | Unit  |
| :------------------------------------------- | :------------------------------ |:----- |
| storage.partitions.count                     | Number of disk partition.       |       |
| *partition\_name*\#storage.space.usage.bytes | Used space on a disk partition. | B     |
| *partition\_name*\#storage.access            | Access disk partition.          |       |

</TabItem>
<TabItem value="Hardware" label="Hardware">

| Metric name                   | Description                               | Unit |
|:----------------------------- |:----------------------------------------- |:---- |
| disk.status                   | Status of the disk                        |      |
| raid.status                   | Status of the raid                        |      |
| fan.status                    | Status of the fan                         |      |
| temperature.status            | Status of the temperature                 |      |
| voltage.status                | Status of the voltage                     |      |
| hardware.fan.speed.rpm        | Speed of fan                              | rpm  |
| hardware.temperature.celsius  | temperature of the different sensors      | C    |
| hardware.voltage.millivolt    | Voltage of the different sensors          | mV   |

</TabItem>
<TabItem value="Interfaces" label="Interfaces">

| Metric name                                                 | Description                                             | Unit |
|:----------------------------------------------------------- |:------------------------------------------------------- |:---- |
| status                                                      | Status of the interface                                 |      |
| *interface\_name*\#interface.traffic.in.bitspersecond       | Incoming traffic going through the interface.           | b/s  |
| *interface\_name*\#interface.traffic.out.bitspersecond      | Outgoing traffic going through the interface.           | b/s  |
| *interface\_name*\#interface.packets.in.error.percentage    | Incoming errored packets going through the interface.   | %    |
| *interface\_name*\#interface.packets.in.discard.percentage  | Incoming discarded packets going through the interface. | %    |
| *interface\_name*\#interface.packets.out.error.percentage   | Outgoing errored packets going through the interface.   | %    |
| *interface\_name*\#interface.packets.out.discard.percentage | Outgoing discarded packets going through the interface. | %    |

</TabItem>
<TabItem value="Memory" label="Memory">

| Metric name              | Description                | Unit |
| :----------------------- | :------------------------- |:---- |
| memory.usage.bytes       | Memory usage               | B    |
| memory.free.bytes        | Free memory                | B    |
| memory.usage.percentage  | Memory usage in percentage | %    |
| memory.buffer.bytes      | Buffer memory              | B    |
| memory.cached.bytes      | Memory cached              | B    |

</TabItem>
</Tabs>

## Prérequis

Afin de contrôler vos équipements Lenovo Iomega, le SNMP v2 doit être configuré.
Pour plus d'information, vous pouvez vous référer à la documentation utilisateur officiel :
http://download.lenovo.com/nasupdate/manuals/px2-300d/px2-300d-4.1-en.pdf#page=69&zoom=100,72,90

## Installation

<Tabs groupId="sync">
<TabItem value="Online License" label="Online License">

1. Installer le Plugin sur tous les Collecteurs Centreon :

```bash
yum install centreon-plugin-Hardware-Storage-Lenovo-Iomega-Snmp
```

2. Sur l'interface Web de Centreon, installer le Pack *Lenovo Iomega* depuis la page **Configuration > Gestionnaire de connecteurs de supervision**

</TabItem>
<TabItem value="Offline License" label="Offline License">

1. Installer le Plugin sur tous les Collecteurs Centreon :

```bash
yum install centreon-plugin-Hardware-Storage-Lenovo-Iomega-Snmp
```

2. Sur le serveur Central Centreon, installer le Pack via le RPM:

```bash
yum install centreon-pack-hardware-storage-lenovo-iomega-snmp
```

3. Sur l'interface Web de Centreon, installer le Pack *Lenovo Iomega* depuis la page **Configuration > Gestionnaire de connecteurs de supervision**

</TabItem>
</Tabs>

## Configuration

* Ajoutez un nouvel Hôte depuis la page **Configuration > Hôtes**
* Complétez les champs *Adresse IP/DNS*, *Communauté SNMP* et *Version SNMP*
* Appliquez le Modèle d'Hôte *HW-Storage-Lenovo-Iomega-SNMP-custom*

> Si vous utilisez SNMP en version 3, vous devez configurer les paramètres spécifiques associés via la macro SNMPEXTRAOPTIONS.
> Plus d'informations dans la section [Troubleshooting SNMP](../getting-started/how-to-guides/troubleshooting-plugins.md#snmpv3-options-mapping). 

| Mandatory   | Name                    | Description                       |
| :---------- | :---------------------- | :---------------------------------|
|             | SNMPEXTRAOPTIONS        | Extra options SNMP                |


## Comment puis-je tester le Plugin et que signifient les options des commandes ?

Une fois le Plugin installé, vous pouvez tester celui-ci directement en ligne de commande depuis un collecteur Centreon en vous connectant avec l'utilisateur *centreon-engine* :

```bash
/usr/lib/centreon/plugins/centreon_lenovo_iomega_snmp.pl
    --plugin=storage::lenovo::iomega::snmp::plugin
    --mode=cpu
    --hostname=10.30.2.114
    --snmp-version='2c'
    --snmp-community='iomega_ro'
    --warning-average='90'
    --critical-average='95'
    --verbose
```

La commande devrait retourner un message de sortie de la forme ci-dessous:

```bash
OK: CPU(s) average usage is 15.29 % - CPU '0' usage : 15.29 % | 'total_cpu_avg'=15.29%;0:90;0:95;0;100 'cpu'=15.29%;;;0;100
```

Cette commande contrôle l'utilisation CPU (```--mode=cpu```) d'un équipement ayant pour adresse *10.30.2.114* (```--hostname=10.30.2.114```) 
en version *2c* du protocol SNMP (```--snmp-version='2c'```) et avec la communauté *iomega_ro* (```--snmp-community='iomega_ro'```).

Cette commande déclenchera une alarme WARNING si l'utilisation moyenne CPU est à plus de 90% (```--warning-average='90'```)
et une alarme CRITICAL si plus de 95% (```--critical-average='95'```).
 
Pour chaque mode, la liste de toutes les métriques, seuils associés et options complémentaires peut être affichée
en ajoutant le paramètre ```--help``` à la commande:

```bash
/usr/lib/centreon/plugins/centreon_lenovo_iomega_snmp.pl
    --plugin=storage::lenovo::iomega::snmp::plugin
    --mode=cpu \
    --help
```

## Diagnostique

[Diagnostique des plugins](../getting-started/how-to-guides/troubleshooting-plugins.md)
