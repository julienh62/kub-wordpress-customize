#installer customize
curl -s https://api.github.com/repos/kubernetes-sigs/kustomize/releases/latest | jq -r .assets[0].browser_download_url | xargs curl -LO
tar -xvzf kustomize_*_linux_amd64.tar.gz
sudo mv kustomize /usr/local/bin

# Vérification du chemin d'exécution de kustomize

Si kustomize n'est pas trouvé, vérifie que le chemin d'installation est bien dans $PATH :

echo $PATH

# Ajout au PATH

Si kustomize n'est pas dans $PATH, ajoute-le à ton chemin d'exécution (par exemple, si tu as installé dans /usr/local/bin):

export PATH=$PATH:/usr/local/bin

Pour rendre cette modification permanente, ajoute cette ligne dans ton fichier ~/.bashrc ou ~/.bash_profile :

echo 'export PATH=$PATH:/usr/local/bin' >> ~/.bashrc
source ~/.bashrc

# Commandes principales avec kustomize

    Appliquer les configurations (build et appliquer les ressources) :

kustomize build ./path/to/kustomization | kubectl apply -f -

Afficher les ressources générées :

kustomize build ./path/to/kustomization

Vérifier les erreurs de configuration :

kustomize edit fix



#se connecter au pod wordpress
kubectl exec -it datascientest-wordpress-657bbb9688-m7dwj -- bash
apt-get update && apt-get install -y nano
nano wp-config.php

