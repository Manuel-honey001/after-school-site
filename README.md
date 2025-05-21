
<🎊AFTER SCHOOL 💯🎟️🎊!>
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
      max-width: 600px;
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
      <legend>Profil</legend>
      <input type="radio" name="profil" value="Délégué" required /> Délégué<br />
      <div id="delegate-options" style="display: none; margin-top: 10px;">
        <label><input type="radio" name="type_delegue" value="BD" /> Bureau Délégué (BD)</label><br />
        <label><input type="radio" name="type_delegue" value="Groupe TD" /> Groupe de TD</label>

        <div id="choix-bd" style="display: none; margin-top: 10px;">
          <select name="poste_bd">
            <option value="">-- Sélectionnez un poste --</option>
            <option value="Délégué principal">Délégué principal</option>
            <option value="SG">SG (Secrétariat Général)</option>
            <option value="SO">SO (Organisation)</option>
            <option value="SP">SP (Projet)</option>
            <option value="SL">SL (Logistique)</option>
            <option value="SC">SC (Communication)</option>
            <option value="Autre">Autre</option>
          </select>
        </div>

        <div id="choix-groupe" style="display: none; margin-top: 10px;">
          <select name="groupe_td">
            <option value="">-- Sélectionnez un groupe --</option>
            <!-- G1 à G25 -->
            <script>
              for (let i = 1; i <= 25; i++) {
                document.write(`<option value="G${i}">G${i}</option>`);
              }
            </script>
          </select>
        </div>
      </div>
      <input type="radio" name="profil" value="Membre du staff" required /> Membre du staff<br />
      <input type="radio" name="profil" value="Non-Délégué" required /> Non-Délégué
    </fieldset>

    <div id="reste-formulaire" style="display: none;">
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
    </div>
  </form>

  <script>
    const profilRadios = document.querySelectorAll('input[name="profil"]');
    const resteForm = document.getElementById('reste-formulaire');
    const delegateOptions = document.getElementById('delegate-options');
    const choixBD = document.getElementById('choix-bd');
    const choixGroupe = document.getElementById('choix-groupe');

    profilRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        resteForm.style.display = 'block';
        if (radio.value === 'Délégué') {
          delegateOptions.style.display = 'block';
        } else {
          delegateOptions.style.display = 'none';
          choixBD.style.display = 'none';
          choixGroupe.style.display = 'none';
        }
      });
    });

    document.querySelectorAll('input[name="type_delegue"]').forEach(radio => {
      radio.addEventListener('change', () => {
        if (radio.value === 'BD') {
          choixBD.style.display = 'block';
          choixGroupe.style.display = 'none';
        } else {
          choixBD.style.display = 'none';
          choixGroupe.style.display = 'block';
        }
      });
    });

    // Allergies
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

    // WhatsApp
    document.getElementById('inscriptionForm').addEventListener('submit', function (e) {
      e.preventDefault();
      const formData = new FormData(this);
      let message = `Nouvelle inscription AFTER SCHOOL :%0A`;
      const profil = formData.get('profil');
      message += `Profil : ${profil}%0A`;

      if (profil === "Délégué") {
        const type = formData.get("type_delegue");
        message += `Type Délégué : ${type}%0A`;
        if (type === "BD") {
          message += `Poste : ${formData.get("poste_bd")}%0A`;
        } else if (type === "Groupe TD") {
          message += `Groupe : ${formData.get("groupe_td")}%0A`;
        }
      }

      message += `Nom : ${formData.get('nom')}%0A`;
      message += `Prénom : ${formData.get('prenom')}%0A`;
      message += `Sexe : ${formData.get('sexe')}%0A`;
      message += `Mail : ${formData.get('mail')}%0A`;
      message += `Contact WhatsApp : ${formData.get('contact')}%0A`;
      message += `Filière : ${formData.get('filiere')}%0A`;
      message += `Niveau : ${formData.get('niveau')}%0A`;
      message += `Allergies : ${formData.get('allergie')}`;
      if (formData.get('allergie') === "Oui") {
        message += ` (${formData.get('detail_allergie')})`;
      }
      message += `%0AAlcool : ${formData.get('alcool')}%0A`;
      message += `Présence : ${formData.get('presence')}`;

      const numeroDest = "225504129645";
      const whatsappURL = `https://wa.me/${numeroDest}?text=${message}`;
      window.open(whatsappURL, '_blank');
    });
  </script>
</body>
</html>
