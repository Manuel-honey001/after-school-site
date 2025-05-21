<! 🎊AFTER SCHOOL🎟️💯🎊>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Inscription AFTER SCHOOL</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Georgia, 'Times New Roman', Times, serif;
      background: url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1920&q=80') no-repeat center center fixed;
      background-size: cover;
      color: white;
    }

    form {
      background: rgba(0, 0, 0, 0.7);
      max-width: 600px;
      margin: 40px auto;
      padding: 30px 40px;
      border-radius: 10px;
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.5);
    }

    fieldset {
      border: none;
      margin-bottom: 18px;
    }

    legend {
      font-weight: bold;
      font-size: 1.1em;
      margin-bottom: 10px;
    }

    label {
      display: block;
      margin-top: 10px;
    }

    .required::after {
      content: " *";
      color: red;
    }

    input[type="text"],
    input[type="email"],
    input[type="tel"],
    select {
      width: 100%;
      padding: 8px;
      margin-top: 6px;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1em;
    }

    input[type="radio"] {
      margin-right: 8px;
    }

    input[type="submit"],
    input[type="reset"] {
      background: #2563eb;
      color: #fff;
      border: none;
      padding: 10px 22px;
      border-radius: 4px;
      font-size: 1em;
      margin-right: 10px;
      cursor: pointer;
    }

    input[type="submit"]:hover,
    input[type="reset"]:hover {
      background: #1e40af;
    }

    h2 {
      text-align: center;
      font-size: 1.8em;
      margin-bottom: 30px;
      text-shadow: 1px 1px 4px black;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <form id="inscriptionForm">
    <h2>Inscription AFTER SCHOOL</h2>

    <fieldset>
      <legend class="required">Profil</legend>
      <label><input type="radio" name="profil" value="Délégué" required> Délégué</label>
      <label><input type="radio" name="profil" value="Membre du staff"> Membre du staff</label>
      <label><input type="radio" name="profil" value="Non-Délégué"> Non-Délégué</label>

      <div id="delegueOptions" class="hidden">
        <label class="required">Type de délégué :</label>
        <select name="typeDelegue" id="typeDelegue">
          <option value="">-- Sélectionnez --</option>
          <option value="Bureau Délégué">Bureau Délégué (BD)</option>
          <option value="Groupe TD">Groupe de TD</option>
        </select>

        <div id="fonctionBDContainer" class="hidden">
          <label class="required">Fonction au Bureau :</label>
          <select name="fonctionBD">
            <option value="">-- Sélectionnez une fonction --</option>
            <option value="Délégué principal">Délégué principal</option>
            <option value="SG">SG (Secrétariat Général)</option>
            <option value="SO">SO (Organisation)</option>
            <option value="SP">SP (Projet)</option>
            <option value="SL">SL (Logistique)</option>
            <option value="SC">SC (Communication)</option>
            <option value="Autre">Autre</option>
          </select>
        </div>

        <div id="groupeTDContainer" class="hidden">
          <label class="required">Groupe TD :</label>
          <select name="groupeTD">
            <option value="">-- Choisir un groupe --</option>
            ${Array.from({ length: 25 }, (_, i) => `<option value="G${i + 1}">G${i + 1}</option>`).join('')}
          </select>
        </div>
      </div>
    </fieldset>

    <fieldset id="mainFields" class="hidden">
      <legend class="required">Nom</legend>
      <input type="text" name="nom" required />

      <legend class="required">Prénom</legend>
      <input type="text" name="prenom" required />

      <legend class="required">Sexe</legend>
      <label><input type="radio" name="sexe" value="Homme" required> Homme</label>
      <label><input type="radio" name="sexe" value="Femme"> Femme</label>
      <label><input type="radio" name="sexe" value="Autre"> Autre</label>

      <legend class="required">Mail</legend>
      <input type="email" name="mail" required />

      <legend class="required">Contact WhatsApp</legend>
      <input type="tel" name="contact" required />

      <legend class="required">Filière</legend>
      <select name="filiere" required>
        <option value="">-- Choisissez votre filière --</option>
        <option value="Géographie">Géographie</option>
        <option value="Histoire">Histoire</option>
        <option value="Philosophie">Philosophie</option>
        <option value="Autre">Autre</option>
      </select>

      <legend class="required">Niveau d'étude</legend>
      <select name="niveau" required>
        <option value="">-- Sélectionnez un niveau --</option>
        <option value="Licence 1">Licence 1</option>
        <option value="Licence 2">Licence 2</option>
        <option value="Licence 3">Licence 3</option>
        <option value="Master 1">Master 1</option>
        <option value="Master 2">Master 2</option>
      </select>

      <legend class="required">Avez-vous des allergies ?</legend>
      <label><input type="radio" name="allergie" value="Oui" required> Oui</label>
      <label><input type="radio" name="allergie" value="Non"> Non</label>
      <input type="text" name="detail_allergie" placeholder="Si oui, lesquelles ?" class="hidden" />

      <legend class="required">Consommez-vous de l'alcool ?</legend>
      <label><input type="radio" name="alcool" value="Oui" required> Oui</label>
      <label><input type="radio" name="alcool" value="Non"> Non</label>

      <legend class="required">Confirmez-vous votre présence ?</legend>
      <label><input type="radio" name="presence" value="Oui" required> Oui, je serai là pour chiller !</label>
    </fieldset>

    <input type="reset" value="Effacer" />
    <input type="submit" value="Envoyer" />
  </form>

  <script>
    const profilRadios = document.querySelectorAll('input[name="profil"]');
    const delegueOptions = document.getElementById('delegueOptions');
    const typeDelegueSelect = document.getElementById('typeDelegue');
    const fonctionBDContainer = document.getElementById('fonctionBDContainer');
    const groupeTDContainer = document.getElementById('groupeTDContainer');
    const mainFields = document.getElementById('mainFields');
    const detailAllergieInput = document.querySelector('input[name="detail_allergie"]');

    profilRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        delegueOptions.classList.add('hidden');
        fonctionBDContainer.classList.add('hidden');
        groupeTDContainer.classList.add('hidden');
        typeDelegueSelect.value = '';
        mainFields.classList.remove('hidden');
        if (radio.value === "Délégué") {
          delegueOptions.classList.remove('hidden');
        }
      });
    });

    typeDelegueSelect.addEventListener('change', () => {
      fonctionBDContainer.classList.add('hidden');
      groupeTDContainer.classList.add('hidden');
      if (typeDelegueSelect.value === "Bureau Délégué") {
        fonctionBDContainer.classList.remove('hidden');
      } else if (typeDelegueSelect.value === "Groupe TD") {
        groupeTDContainer.classList.remove('hidden');
      }
    });

    document.querySelectorAll('input[name="allergie"]').forEach(r => {
      r.addEventListener('change', () => {
        if (r.value === "Oui") {
          detailAllergieInput.classList.remove('hidden');
        } else {
          detailAllergieInput.classList.add('hidden');
          detailAllergieInput.value = '';
        }
      });
    });

    document.getElementById('inscriptionForm').addEventListener('submit', function (e) {
      e.preventDefault();
      const formData = new FormData(this);
      let message = "Nouvelle inscription AFTER SCHOOL :%0A";
      message += `Profil : ${formData.get('profil')}%0A`;
      if (formData.get('profil') === "Délégué") {
        message += `Type : ${formData.get('typeDelegue')}%0A`;
        if (formData.get('typeDelegue') === "Bureau Délégué") {
          message += `Fonction : ${formData.get('fonctionBD')}%0A`;
        } else {
          message += `Groupe TD : ${formData.get('groupeTD')}%0A`;
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

      const numero = "2250142889555";
      const whatsappURL = `https://wa.me/${numero}?text=${message}`;
      window.open(whatsappURL, '_blank');
    });
  </script>
</body>
</html>
h
