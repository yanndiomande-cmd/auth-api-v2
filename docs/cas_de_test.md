\# Cas de test - ISPA Pay / auth-api-v2



\## CT-01 - Inscription avec donnees valides

Etapes : POST /api/register avec nom, email, mot de passe valide

Resultat attendu : 201, compte cree



\## CT-02 - Inscription avec email deja utilise

Etapes : POST /api/register avec un email deja existant

Resultat attendu : 422, erreur "email deja pris"



\## CT-03 - Inscription avec mot de passe trop court

Etapes : POST /api/register avec mot de passe < 8 caracteres

Resultat attendu : 422, erreur de validation



\## CT-04 - Connexion avec bons identifiants

Etapes : POST /api/login avec email + bon mot de passe

Resultat attendu : 200, token retourne



\## CT-05 - Connexion avec mauvais mot de passe

Etapes : POST /api/login avec mauvais mot de passe

Resultat attendu : 401, message "identifiants invalides"



\## CT-06 - Acces route protegee sans token

Etapes : GET /api/user sans token

Resultat attendu : 401, non autorise



\## CT-07 - Acces route protegee avec token valide

Etapes : GET /api/user avec token valide

Resultat attendu : 200, infos utilisateur retournees

