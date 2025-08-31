# DiversiTech

> **Plateforme éducative moderne** pour la gestion des devoirs et ressources pédagogiques.

## � Comment Lancer le Projet

### ⚠️ IMPORTANT : Cloner TOUS les Repositories

Le projet DiversiTech est organisé en **plusieurs repositories séparés**. Vous devez **tous les cloner** dans le même dossier :

```bash
# 1. Créer un dossier pour le projet complet
mkdir DiversiTech
cd DiversiTech

# 2. Cloner TOUS les repositories (obligatoire)
git clone https://github.com/DevoirsiTech/.github.git
git clone https://github.com/DevoirsiTech/devoirsitech-backend.git
git clone https://github.com/DevoirsiTech/devoirsitech-frontend.git
git clone https://github.com/DevoirsiTech/devoirsitech-fileserver.git
git clone https://github.com/DevoirsiTech/devoirsitech-infra.git
git clone https://github.com/DevoirsiTech/devoirsitech-doc.git
```

### 🚀 Lancement de l'Environnement

```bash
# 3. Aller dans le dossier d'infrastructure
cd devoirsitech-infra

# 4. Lancer avec WSL (OBLIGATOIRE)
wsl
./run.sh start

# 5. Vérifier que tout fonctionne
./run.sh check
```

### ✅ Vérification du Succès

Une fois lancé, vous devriez pouvoir accéder à :

- **Frontend** : http://app.localhost
- **API Backend** : http://api.localhost
- **FileServer** : http://files.localhost
- **SonarQube** : http://sonar.localhost

Si tous ces liens fonctionnent, **c'est bon !** 🎉

## 🔧 Prérequis Techniques

- **Windows 10/11** avec WSL2 activé
- **Docker Desktop** installé et démarré
- **Git** installé
- **Au moins 8GB de RAM** (recommandé)

### Installation WSL (si pas encore fait)

```powershell
# Dans PowerShell en tant qu'administrateur
wsl --install
# Redémarrer puis configurer Ubuntu
```

## � Structure du Projet

```
DiversiTech/
├── .github/                 # Configuration GitHub & CI/CD
├── devoirsitech-backend/    # API ASP.NET Core (port 5001)
├── devoirsitech-frontend/   # Interface React + TypeScript (port 3000)
├── devoirsitech-fileserver/ # Service de fichiers (port 5002)
├── devoirsitech-infra/      # 🎯 Scripts de lancement Docker
└── devoirsitech-doc/        # Documentation du projet
```

## 🆘 Problèmes Courants

### ❌ "Services ne démarrent pas"
```bash
# Vérifier Docker
docker --version
docker compose --version

# Redémarrer Docker Desktop
# Puis relancer : ./run.sh start
```

### ❌ "Impossible d'accéder aux URLs"
```bash
# Vérifier les hosts (fait automatiquement par le script)
cat /etc/hosts | grep localhost

# Si pas de configuration, relancer :
./run.sh start
```

### ❌ "Repository manquant"
- **Vérifiez** que vous avez cloné TOUS les 6 repositories
- **Vérifiez** qu'ils sont dans le même dossier parent `DiversiTech/`

## 💡 Commandes Utiles

```bash
# Voir l'aide complète
./run.sh help

# Arrêter tous les services
./run.sh reset

# Relancer proprement
./run.sh start

# Vérifier l'état
./run.sh check
```

---

**🎉 Votre environnement DiversiTech est maintenant prêt !**

Pour le développement, consultez la documentation dans chaque repository spécifique.
