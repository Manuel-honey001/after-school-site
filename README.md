inscriptions.htlm
<!DOCTYPE html>
<html lang="fr">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Formulaire d'Inscription</title>
  <style>
    body {
      background: #f5f7fa;
      font-family: Georgia, 'Times New Roman', Times, serif;
      margin: 0;
      padding: 0;
      background-color: #d1d5db;
    }

    form {
      background: #5787f0;
      max-width: 500px;
      margin: 40px auto;
      padding: 30px 40px;
      border-radius: 10px;
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
      color: white;
    }

    fieldset {
      border: 1px solid #d1d5db;
      border-radius: 6px;
      margin-bottom: 18px;
      padding: 15px 18px;
    }

    legend {
      font-weight: bold;
      color: #ffffff;
      padding: 0 8px;
    }

    input[type="text"],
    input[type="email"],
    input[type="tel"],
    select {
      width: 95%;
      padding: 8px;
      margin: 8px 0 12px 0;
      border: 1px solid #cbd5e1;
      border-radius: 4px;
      font-size: 1em;
      background: #f9fafb;
      color: #000;
    }

    input[type="radio"] {
      margin-right: 8px;
    }

    input[type="reset"],
    input[type="submit"] {
      background: #2563eb;
      color: #fff;
      border: none;
      padding: 10px 22px;
      border-radius: 4px;
      font-size: 1em;
      margin-right: 10px;
      cursor: pointer;
      transition: background 0.2s;
    }

    input[type="reset"]:hover,
    input[type="submit"]:hover {
      background: #1e40af;
    }

    p {
      text-align: center;
    }

    a {
      color: #fff;
      font-weight: bold;
      text-decoration: underline;
    }
  </style>
</head>

<body>
  <form id="inscriptionForm">
    <fieldset>
      <legend>Nom</legend>
      <input type="text" name="nom" placeholder="Votre nom" required />
    </fieldset>

    <fieldset>
      <legend>Prénom</legend>
      <input type="text" name="prenom" placeholder="Votre prénom" required />
    </fieldset>

    <fieldset>
      <legend>Sexe</legend>
      <input type="radio" name="sexe" value="Homme" required /> Homme<br />
      <input type="radio" name="sexe" value="Femme" required /> Femme<br />
      <input type="radio" name="sexe" value="Autre" required /> Autre
    </fieldset>

    <fieldset>
      <legend>Mail</legend>
      <input type="email" name="mail" placeholder="Votre mail" required />
    </fieldset>

    <fieldset>
      <legend>Contact WhatsApp</legend>
      <input type="tel" name="contact" placeholder="Numéro WhatsApp" required />
    </fieldset>

    <fieldset>
      <legend>Filière</legend>
      <select name="filiere" required>
        <option value="">-- Choisissez votre filière --</option>
        <option value="Géographie">Géographie</option>
        <option value="Histoire">Histoire</option>
        <option value="Philosophie">Philosophie</option>
        <option value="Autre">Autre</option>
      </select>
    </fieldset>

    <fieldset>
      <legend>Niveau d'étude</legend>
      <select name="niveau" required>
        <option value="">-- Sélectionnez un niveau --</option>
        <option value="Licence 1">Licence 1</option>
        <option value="Licence 2">Licence 2</option>
        <option value="Licence 3">Licence 3</option>
        <option value="Master 1">Master 1</option>
        <option value="Master 2">Master 2</option>
      </select>
    </fieldset>

    <fieldset>
      <legend>Avez-vous des allergies ?</legend>
      <input type="radio" name="allergie" value="Oui" required /> Oui<br />
      <input type="radio" name="allergie" value="Non" required /> Non<br />
      <div id="detail-allergie-container" style="display:none;">
        <input type="text" name="detail_allergie" placeholder="Si oui, lesquelles ?" />
      </div>
    </fieldset>

    <fieldset>
      <legend>Consommez-vous de l'alcool ?</legend>
      <input type="radio" name="alcool" value="Oui" required /> Oui<br />
      <input type="radio" name="alcool" value="Non" required /> Non
    </fieldset>

    <fieldset>
      <legend>Confirmez-vous votre présence ?</legend>
      <input type="radio" name="presence" value="Oui" required /> Oui, je serai là pour chiller !
    </fieldset>

    <input type="reset" value="Effacer" />
    <input type="submit" value="Envoyer" />
    <p><strong>Merci de votre participation</strong></p>
  </form>

  <p>
    <a href="AFTER SCHOOL insription.html">&#8592; Retour à l'accueil</a>
  </p>

  <script>
    // Gestion du champ détail allergie
    function toggleAllergieDetail() {
      const ouiRadio = document.querySelector('input[name="allergie"][value="Oui"]');
      const detailContainer = document.getElementById('detail-allergie-container');
      if (ouiRadio.checked) {
        detailContainer.style.display = "block";
      } else {
        detailContainer.style.display = "none";
        detailContainer.querySelector('input[name="detail_allergie"]').value = "";
      }
    }
    document.querySelectorAll('input[name="allergie"]').forEach(radio => {
      radio.addEventListener('change', toggleAllergieDetail);
    });
    window.addEventListener('load', toggleAllergieDetail);

    // À la soumission du formulaire
    document.getElementById('inscriptionForm').addEventListener('submit', function (e) {
      e.preventDefault(); // empêche l'envoi normal

      // Récupérer les données du formulaire
      const formData = new FormData(this);

      // Construire le message WhatsApp
      let message = "Nouvelle inscription AFTER SCHOOL :%0A";
      message += `Nom : ${formData.get('nom')}%0A`;
      message += `Prénom : ${formData.get('prenom')}%0A`;
      message += `Sexe : ${formData.get('sexe')}%0A`;
      message += `Mail : ${formData.get('mail')}%0A`;
      message += `Contact WhatsApp : ${formData.get('contact')}%0A`;
      message += `Filière : ${formData.get('filiere')}%0A`;
      message += `Niveau d'étude : ${formData.get('niveau')}%0A`;
      message += `Allergies : ${formData.get('allergie')}`;
      if (formData.get('allergie') === "Oui") {
        message += ` (${formData.get('detail_allergie')})`;
      }
      message += `%0AConsommation d'alcool : ${formData.get('alcool')}%0A`;
      message += `Présence confirmée : ${formData.get('presence')}`;

      // Numéro WhatsApp destinataire (ton numéro)
      const numeroDest = "2250142889555"; // sans le 0 initial, code pays 225 ici pour Côte d'Ivoire

      // URL WhatsApp pour envoyer le message
      const whatsappURL = `https://wa.me/${numeroDest}?text=${message}`;

      // Ouvrir WhatsApp dans un nouvel onglet pour envoyer le message
      window.open(whatsappURL, '_blank');

      // Rediriger vers le lien de paiement Wave après 1 seconde
      setTimeout(() => {
        window.location.href = "https://pay.wave.com/m/M_ci_PosgFP_Yw3Xu/c/ci/?amount=8000";
      }, 1000);
    });
  </script>
</body>

</html>
