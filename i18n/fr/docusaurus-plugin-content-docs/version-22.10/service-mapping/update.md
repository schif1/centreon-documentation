---
id: update
title: Mettre à jour l'extension
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## Mise à jour du paquet

Afin de mettre à jour le module **Centreon BAM**, lancer la commande
ci-dessous :

<Tabs groupId="sync">
<TabItem value="Alma / RHEL / Oracle Linux 8" label="Alma / RHEL / Oracle Linux 8">

```shell
dnf update centreon-bam-server
```

</TabItem>
<TabItem value="CentOS 7" label="CentOS 7">

```shell
yum update centreon-bam-server
```

</TabItem>
<TabItem value="Debian 11" label="Debian 11">

```shell
apt update && apt install --only-upgrade centreon-bam-server
```

</TabItem>
</Tabs>

## Mise à jour de l'interface

Se connecter à l'interface web de Centreon et se rendre dans le menu
`Administration > Extensions > Gestionnaire`.

Un bouton orange de mise à jour est visible et signale qu'une mise à
jour est disponible, cliquez dessus pour mettre à jour le module, faire
de même pour le widget.
