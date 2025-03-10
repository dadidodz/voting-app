# Utilisation d'une image Python légère
FROM python:3.9

# Définition du répertoire de travail
WORKDIR /azure-vote

# Copier les fichiers nécessaires
COPY . /azure-vote

# Installer les dépendances
RUN pip install --no-cache-dir flask redis requests

# Définir les variables d'environnement (elles peuvent être surchargées dans docker-compose)
ENV REDIS=redis

# Exposer le port 80
EXPOSE 80

# Ajouter un healthcheck
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
  CMD curl -f http://localhost:80 || exit 1

# Commande pour lancer l'application
CMD ["python", "main.py"]
