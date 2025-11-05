#test_gdm.py

# Dictionnaire global pour stocker les mots de passe par service
mots_de_passe = {}

# Fonction pour ajouter un mot de passe à un service
def ajouter_mdp(service, identifiant, mot_de_passe):
    
    mots_de_passe[service] = {
        'identifiant': identifiant,           
        'mot_de_passe': mot_de_passe    
    }
    print(f"✅ [service] 🔐 **{service}** → **{identifiant}**")

# Fonction pour afficher les informations d'un service
    def afficher_mdp(service):
    if service in mots_de_passe:
        infos = mots_de_passe[service]
        print(f"📂 Service: **{service}**")
        print(f"👤 Identifiant: {infos['identifiant']}")
        print(f"🔑 Mot de passe: {infos['mot_de_passe']}")
    else:
        print("❌ Aucun mot de passe trouvé pour ce service.")

# Fonction pour supprimer un mot de passe (PLACÉE CORRECTEMENT)
    def supprimer_mdp(service):
    if service in mots_de_passe:
        del mots_de_passe[service]
        print(f"🗑️ [Supprimé] **{service}**")
    else:
        print("❌ Aucun mot de passe trouvé pour ce service.")

# Boucle principale du programme (PLACÉE CORRECTEMENT)
    while True:
    print("\n🦅 === MENU ÉPERVIER ===")
    
   # Affichage des options 
    print("1️⃣ Ajouter un mot de passe")
    print("2️⃣ Afficher un mot de passe")
    print("3️⃣ Supprimer un mot de passe")
    print("4️⃣ Quitter")
    
   # Lecture du choix de l'utilisateur
    choix = input("🎯 Ton choix, agent Épervier: ")

   # Traitement du choix
    if choix == '1':
        service = input("🔧 Nom du service: ")
        identifiant = input("👤 Identifiant: ")
        mot_de_passe = input("🔑 Mot de passe: ")
        ajouter_mdp(service, identifiant, mot_de_passe)

    elif choix == '2':
        service = input("🔍 Nom du service à afficher: ")
        afficher_mdp(service)

    elif choix == '3':
        service = input("🧹 Nom du service à supprimer: ")
        supprimer_mdp(service)

    elif choix == '4':
        print("🛑 Mission terminée. À bientôt, agent Épervier !")
        break # Utiliser 'break' pour sortir de la boucle 'while True'

    else:
        print("❓ Choix invalide. Réessaie avec les touches 1 à 4.")
