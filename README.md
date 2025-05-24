
 FONCTIONNALITES DevOps

- CI/CD AVEC GITHUB ACTIONS 
  Build, push des images Docker sur DockerHub, et déploiement automatique via SSH.

-  CONTEUNEURISATION AVEC DOCKER 
  Chaque composant (frontend, backend, base de données, reverse proxy) est conteneurisé.

-  REVERSE PROXY AVEC NGINX 
  Permet d’exposer le frontend sur le port 80, tout en redirigeant les requêtes API vers le backend.

DEPLOIEMENT AUTOMATIQUE

Le pipeline se déclenche sur un push vers la branche `main`.  
Il exécute les étapes suivantes :

1. Build des images Docker (frontend et backend)
2. Push vers DockerHub
3. Connexion SSH au serveur distant
4. Pull du code & redémarrage des services via `docker-compose`

 SECRETS GITHUB NECCESSAIRE

- DOCKER_USERNAME
- DOCKER_TOKEN
- REMOTE_HOST
- REMOTE_USER
- REMOTE_SSH_KEY (clé privée SSH, encodée en base64)

Docker Compose – Services

- backend : Node.js API
- frontend : Interface utilisateur Vue.js
- postgres : Base de données PostgreSQL
- reverse-proxy : Serveur NGINX

PORTS EXPOSE
             
Frontend      8081          80
Backend API   9001          9001
PostgreSQL    5432          5432
Reverse Proxy 80            80    

       |

