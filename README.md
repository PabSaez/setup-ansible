# Setup Ansible pour Ubuntu

Ce guide vous accompagne dans l'installation et la configuration de votre environnement Ubuntu à l'aide d'Ansible.

## Prérequis

Avant de commencer, assurez-vous que vous avez installé Ubuntu et configuré un utilisateur avec des privilèges sudo.

## Installation d'Ansible

Après avoir terminé l'installation de l'OS Ubuntu, suivez les étapes ci-dessous pour installer Ansible :

1. Mettez à jour la liste des paquets et installez les dépendances nécessaires :

    ```bash
    sudo apt update
    sudo apt install -y software-properties-common
    ```

2. Ajoutez le dépôt officiel d'Ansible et installez Ansible :

    ```bash
    sudo add-apt-repository --yes --update ppa:ansible/ansible
    sudo apt install -y ansible
    ```

## Cloner le Répertoire du Playbook

Choisissez un répertoire de travail et clonez le dépôt Git contenant le playbook Ansible :

```bash
git clone git@github.com:PabSaez/setup-ansible.git
```

Naviguez ensuite dans le répertoire cloné :

```bash
cd setup-ansible
```

## Exécution du Playbook

Une fois dans le répertoire du projet, exécutez le playbook pour installer et configurer votre système avec les logiciels et configurations souhaités :

```bash
ansible-playbook -i inventory.ini install_linux.yml
```

### Remarques :

- **inventory.ini** : Ce fichier d'inventaire est utilisé pour spécifier que le playbook doit s'exécuter sur la machine locale (localhost).
- **install_linux.yml** : Ce playbook contient toutes les tâches d'installation et de configuration.

## Personnalisation

Si vous souhaitez personnaliser le playbook pour ajouter ou supprimer des logiciels, modifiez simplement le fichier `install_linux.yml` avant d'exécuter Ansible.

## Conclusion

Après avoir exécuté le playbook, votre système Ubuntu devrait être configuré avec tous les logiciels et paramètres nécessaires pour votre utilisation quotidienne. Vous pouvez réutiliser ce setup sur d'autres machines Ubuntu en suivant les mêmes étapes.
