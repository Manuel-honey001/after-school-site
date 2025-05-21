<! AFTER SCOOL 🎟️💯🎊>
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

    label.required::after {
      content: " *";
      color: red;
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

    .hidden {
      display: none;
    }
  </style>
</head>

<body>
  <form id="inscriptionForm">
    <!-- Profil -->
    <fieldset>
      <legend><label class="required">Profil</label></legend>
      <input type="radio" name="profil" value="Délégué" required /> Délégué<br />
      <input type="radio" name="profil" value="Membre du staff" required /> Membre du staff<br />
      <input type="radio" name="profil" value="Non-Délégué" required /> Non-Délégué
    </fieldset>

    <!-- Bloc détaillé affiché selon profil -->
    <div id="form-details" class="hidden">

      <!-- Délégué -->
      <div id="details-delegue" class="hidden">
        <fieldset>
          <legend><label class="required">Type de Délégué</label></legend>
          <input type="radio" name="type_delegue" value="Groupe TD" required /> Groupe TD<br />
          <input type="radio" name="type_delegue" value="Bureau des délégués" required /> Bureau des délégués
        </fieldset>

        <div id="delegue-groupe" class="hidden">
          <fieldset>
            <legend><label class="required">Groupe de TD (1 à 30)</label></legend>
            <select name="groupe_td" required>
              <option value="">-- Sélectionnez un groupe --</option>
              <!-- Générer les options 1 à 30 -->
              <script>
                for (let i = 1; i <= 30; i++) {
                  document.write(`<option value="${i}">${i}</option>`);
                }
              </script>
            </select>
          </fieldset>
        </div>

        <div id="bureau-delegues" class="hidden">
          <fieldset>
            <legend><label class="required">Poste au Bureau des délégués</label></legend>
            <select name="poste_bureau" required>
              <option value="">-- Sélectionnez un poste --</option>
              <option value="Délégué principal">Délégué principal</option>
              <option value="SG (Secrétariat général)">SG (Secrétariat général)</option>
              <option value="SO (Secrétariat à l'organisation)">SO (Secrétariat à l'organisation)</option>
              <option value="SCP (Secrétariat chargé des projets)">SCP (Secrétariat chargé des projets)</option>
              <option value="SC (Secrétariat à la communication)">SC (Secrétariat à la communication)</option>
              <option value="Autre">Autre</option>
            </select>
            <input type="text" name="poste_bureau_autre" placeholder="Précisez si autre" class="hidden" />
          </fieldset>
        </div>
      </div>

      <!-- Membre du staff -->
      <div id="staff-options" class="hidden">
        <fieldset>
          <legend><label class="required">Fonction dans le staff</label></legend>
          <select name="fonction_staff" required>
            <option value="">-- Sélectionnez une fonction --</option>
            <option value="PCO principal">PCO principal</option>
            <option value="PCO adjoint">PCO Adjoint</option>
            <option value="Commission logistique">Commission logistique</option>
            <option value="Commission communication">Commission communication</option>
            <option value="Commission restauration">Commission restauration</option>
            <option value="Commission décoration">Commission décoration</option>
            <option value="Autre">Autre</option>
          </select>
          <input type="text" name="autre_fonction_staff" placeholder="Précisez si autre" class="hidden" />
        </fieldset>
      </div>

      <!-- Non-Délégué ou les autres champs généraux -->
      <fieldset>
        <legend><label class="required">Nom</label></legend>
        <input type="text" name="nom" placeholder="Votre nom" required />
      </fieldset>

      <fieldset>
        <legend><label class="required">Prénom</label></legend>
        <input type="text" name="prenom" placeholder="Votre prénom" required />
      </fieldset>

      <fieldset>
        <legend><label class="required">Sexe</label></legend>
        <input type="radio" name="sexe" value="Homme" required /> Homme<br />
        <input type="radio" name="sexe" value="Femme" required /> Femme<br />
        <input type="radio" name="sexe" value="Autre" required /> Autre
      </fieldset>

      <fieldset>
        <legend><label class="required">Mail</label></legend>
        <input type="email" name="mail" placeholder="Votre mail" required />
      </fieldset>

      <fieldset>
        <legend><label class="required">Contact WhatsApp</label></legend>
        <input type="tel" name="contact" placeholder="Numéro WhatsApp" required />
      </fieldset>

      <fieldset>
        <legend><label class="required">Filière</label></legend>
        <select name="filiere" required>
          <option value="">-- Choisissez votre filière --</option>
          <option value="Géographie">Géographie</option>
          <option value="Histoire">Histoire</option>
          <option value="Philosophie">Philosophie</option>
          <option value="Autre">Autre</option>
        </select>
      </fieldset>

      <fieldset>
        <legend><label class="required">Niveau d'étude</label></legend>
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
        <legend><label class="required">Avez-vous des allergies ?</label></legend>
        <input type="radio" name="allergie" value="Oui" required /> Oui<br />
        <input type="radio" name="allergie" value="Non" required /> Non<br />
        <div id="detail-allergie-container" style="display:none;">
          <input type="text" name="detail_allergie" placeholder="Si oui, lesquelles ?" />
        </div>
      </fieldset>

      <fieldset>
        <legend><label class="required">Consommez-vous de l'alcool ?</label></legend>
        <input type="radio" name="alcool" value="Oui" required /> Oui<br />
        <input type="radio" name="alcool" value="Non" required /> Non
      </fieldset>

      <fieldset>
        <legend><label class="required">Confirmez-vous votre présence ?</label></legend>
        <input type="radio" name="presence" value="Oui" required /> Oui, je serai là pour chiller !
      </fieldset>

    </div>

    <input type="reset" value="Effacer" />
    <input type="submit" value="Envoyer" />
    <p><strong>Merci de votre participation</strong></p>
  </form>

  <p>
    <a href="https://manuel-honey001.github.io/SORTIE/">&#8592; Retour à l'accueil</a>
  </p>

  <script>
    // Gestion affichage formulaire détail selon profil
    const profilRadios = document.querySelectorAll('input[name="profil"]');
    const formDetails = document.getElementById('form-details');
    const detailsDelegue = document.getElementById('details-delegue');
    const staffOptions = document.getElementById('staff-options');

    profilRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        formDetails.classList.remove('hidden');
        const profil = radio.value;
        detailsDelegue.classList.toggle('hidden', profil !== 'Délégué');
        staffOptions.classList.toggle('hidden', profil !== 'Membre du staff');
      });
    });

    // Gestion Délégué : affichage groupe TD ou bureau délégués
    const typeDelegueRadios = document.querySelectorAll('input[name="type_delegue"]');
    const delegueGroupe = document.getElementById('delegue-groupe');
    const bureauDelegues = document.getElementById('bureau-delegues');

    typeDelegueRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        delegueGroupe.classList.toggle('hidden', radio.value !== 'Groupe TD');
        bureauDelegues.classList.toggle('hidden', radio.value !== 'Bureau des délégués');
        // Clear other inputs when switching
        if (radio.value === 'Groupe TD') {
          bureauDelegues.querySelector('select').value = "";
          bureauDelegues.querySelector('input[name="poste_bureau_autre"]').value = "";
          bureauDelegues.querySelector('input[name="poste_bureau_autre"]').classList.add('hidden');
        } else {
          delegueGroupe.querySelector('select').value = "";
        }
      });
    });

    // Autre poste bureau délégués
    const posteBureauSelect = document.querySelector('select[name="poste_bureau"]');
    const posteBureauAutreInput = document.querySelector('input[name="poste_bureau_autre"]');
    posteBureauSelect.addEventListener('change', () => {
      posteBureauAutreInput.classList.toggle('hidden', posteBureauSelect.value !== 'Autre');
      if (posteBureauSelect.value !== 'Autre') {
        posteBureauAutreInput.value = "";
      }
    });

    // Autre fonction staff
    const fonctionStaffSelect = document.querySelector('select[name="fonction_staff"]');
    const autreFonctionStaffInput = document.querySelector('input[name="autre_fonction_staff"]');
    fonctionStaffSelect.addEventListener('change', () => {
      autreFonctionStaffInput.classList.toggle('hidden', fonctionStaffSelect.value !== 'Autre');
      if (fonctionStaffSelect.value !== 'Autre') {
        autreFonctionStaffInput.value = "";
      }
    });

    // Gestion champ détail allergie
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

    // Soumission du formulaire
    document.getElementById('inscriptionForm').addEventListener('submit', function (e) {
      e.preventDefault();

      const data = new FormData(this);

      // Vérifications supplémentaires pour les champs affichés dynamiquement
      const profil = data.get('profil');
      if (!profil) {
        alert("Veuillez sélectionner un profil.");
        return;
      }

      if (profil === "Délégué") {
        const typeDelegue = data.get('type_delegue');
        if (!typeDelegue) {
          alert("Veuillez sélectionner le type de délégué.");
          return;
        }
        if (typeDelegue === "Groupe TD" && !data.get('groupe_td')) {
          alert("Veuillez sélectionner un groupe TD.");
          return;
        }
        if (typeDelegue === "Bureau des délégués") {
          const posteBureau = data.get('poste_bureau');
          if (!posteBureau) {
            alert("Veuillez sélectionner un poste au bureau des délégués.");
            return;
          }
          if (posteBureau === "Autre" && !data.get('poste_bureau_autre').trim()) {
            alert("Veuillez préciser le poste au bureau des délégués.");
            return;
          }
        }
      }

      if (profil === "Membre du staff") {
        const fonctionStaff = data.get('fonction_staff');
        if (!fonctionStaff) {
          alert("Veuillez sélectionner une fonction dans le staff.");
          return;
        }
        if (fonctionStaff === "Autre" && !data.get('autre_fonction_staff').trim()) {
          alert("Veuillez préciser la fonction dans le staff.");
          return;
        }
      }

      // Construire le message WhatsApp
      let message = "Nouvelle inscription AFTER SCHOOL :%0A";
      message += `Profil : ${profil}%0A`;

      if (profil === "Délégué") {
        message += `Type délégué : ${data.get('type_delegue')}%0A`;
        if (data.get('type_delegue') === "Groupe TD") {
          message += `Groupe TD : ${data.get('groupe_td')}%0A`;
        } else {
          let poste = data.get('poste_bureau');
          if (poste === "Autre") {
            poste += ` (${data.get('poste_bureau_autre')})`;
          }
          message += `Poste bureau des délégués : ${poste}%0A`;
        }
      } else if (profil === "Membre du staff") {
        let fonction = data.get('fonction_staff');
        if (fonction === "Autre") {
          fonction += ` (${data.get('autre_fonction_staff')})`;
        }
        message += `Fonction staff : ${fonction}%0A`;
      }

      // Champs communs
      message += `Nom : ${data.get('nom')}%0A`;
      message += `Prénom : ${data.get('prenom')}%0A`;
      message += `Sexe : ${data.get('sexe')}%0A`;
      message += `Mail : ${data.get('mail')}%0A`;
      message += `Contact WhatsApp : ${data.get('contact')}%0A`;
      message += `Filière : ${data.get('filiere')}%0A`;
      message += `Niveau d'étude : ${data.get('niveau')}%0A`;
      message += `Allergies : ${data.get('allergie')}`;
      if (data.get('allergie') === "Oui") {
        message += ` (${data.get('detail_allergie')})`;
      }
      message += `%0AConsommation d'alcool : ${data.get('alcool')}%0A`;
      message += `Présence confirmée : ${data.get('presence')}`;

      // Num
