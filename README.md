inscriptions.html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Formulaire rapide</title>
  <script>
    function envoyerParWhatsApp(event) {
      event.preventDefault(); // Empêche l'envoi classique

      // Récupération des champs
      const nom = document.getElementById("nom").value;
      const prenom = document.getElementById("prenom").value;
      const sexe = document.querySelector('input[name="sexe"]:checked')?.value || '';
      const mail = document.getElementById("mail").value;
      const contact = document.getElementById("contact").value;
      const filiere = document.getElementById("filiere").value;
      const niveau = document.getElementById("niveau").value;

      // Construire le message
      const message = `
Nouvelle inscription :
Nom : ${nom}
Prénom : ${prenom}
Sexe : ${sexe}
Email : ${mail}
Contact WhatsApp : ${contact}
Filière : ${filiere}
Niveau : ${niveau}
      `;

      // Numéro WhatsApp du destinataire (ex. : +2250504129645)
      const numero = "22504129645";

      // Ouvre WhatsApp dans un nouvel onglet
      window.open(`https://wa.me/${numero}?text=${encodeURIComponent(message)}`, "_blank");

      // Redirige vers la page de paiement
      window.location.href = "https://manuel-honey001.github.io/After-school-/";
    }
  </script>
</head>
<body>
  <form onsubmit="envoyerParWhatsApp(event)">
    <label>Nom : <input type="text" id="nom" required></label><br>
    <label>Prénom : <input type="text" id="prenom" required></label><br>
    <label>Sexe :
      <input type="radio" name="sexe" value="Homme" required> Homme
      <input type="radio" name="sexe" value="Femme"> Femme
    </label><br>
    <label>Email : <input type="email" id="mail" required></label><br>
    <label>Contact WhatsApp : <input type="tel" id="contact" required></label><br>
    <label>Filière :
      <select id="filiere" required>
        <option value="">-- Choisissez --</option>
        <option value="Géographie">Géographie</option>
        <option value="Histoire">Histoire</option>
        <option value="Philosophie">Philosophie</option>
        <option value="Autre">Autre</option>
      </select>
    </label><br>
    <label>Niveau :
      <select id="niveau" required>
        <option value="">-- Niveau --</option>
        <option value="Licence 1">Licence 1</option>
        <option value="Licence 2">Licence 2</option>
        <option value="Licence 3">Licence 3</option>
        <option value="Master 1">Master 1</option>
        <option value="Master 2">Master 2</option>
      </select>
    </label><br><br>

    <button type="submit">Envoyer</button>
  </form>
</body>
</html>
