<!DOCTYPE html><html lang="fr"><head>
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
    }form {
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
  color: #ff0000;
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

.hidden {
  display: none;
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
</head><body>
  <form id="inscriptionForm">
    <fieldset>
      <legend>Profil <span style="color: red;">*</span></legend>
      <input type="radio" name="profil" value="Délégué" required /> Délégué<br />
      <input type="radio" name="profil" value="Membre du staff" required /> Membre du staff<br />
      <input type="radio" name="profil" value="Non-Délégué" required /> Non-Délégué
    </fieldset><div id="detailsSupplementaires" class="hidden">
  <div id="delegueOptions" class="hidden">
    <fieldset>
      <legend>Détails Délégué <span style="color: red;">*</span></legend>
      <label><input type="radio" name="typeDelegue" value="Groupe TD" /> Groupe TD</label><br />
      <label><input type="radio" name="typeDelegue" value="Bureau des délégués" /> Bureau des délégués</label>

      <div id="groupeTD" class="hidden">
        <label for="groupeTDSelect" class="required">Numéro du groupe :</label>
        <select id="groupeTDSelect" name="groupeTD">
          <option value="">-- Sélectionnez --</option>
          <!-- Options 1 à 30 -->
          " + Array.from({length: 30}, (_, i) => `<option value="${i+1}">${i+1}</option>`).join('') + "
        </select>
      </div>

      <div id="bureauDelegue" class="hidden">
        <label for="bureauSelect" class="required">Fonction :</label>
        <select id="bureauSelect" name="fonctionDelegue">
          <option value="">-- Sélectionnez --</option>
          <option value="Délégué principal">Délégué principal</option>
          <option value="SG">SG (secrétariat général)</option>
          <option value="SO">SO (secrétariat à l'organisation)</option>
          <option value="SCP">SCP (secrétariat chargé des projets)</option>
          <option value="SC">SC (secrétariat à la communication)</option>
          <option value="Autre">Autre</option>
        </select>
        <div id="autreFonctionDelegue" class="hidden">
          <input type="text" name="fonctionAutreDelegue" placeholder="Précisez la fonction" />
        </div>
      </div>
    </fieldset>
  </div>

  <!-- Les autres champs du formulaire apparaissent ici (nom, prénom, etc.) -->
  <!-- ... vous pouvez insérer les autres champs déjà présents ... -->
</div>

<input type="reset" value="Effacer" />
<input type="submit" value="Envoyer" />
<p><strong>Merci de votre participation</strong></p>

  </form>  <script>
    const profilRadios = document.querySelectorAll('input[name="profil"]');
    const detailsSupp = document.getElementById('detailsSupplementaires');
    const delegueOptions = document.getElementById('delegueOptions');

    profilRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        detailsSupp.classList.remove('hidden');
        if (radio.value === 'Délégué') {
          delegueOptions.classList.remove('hidden');
        } else {
          delegueOptions.classList.add('hidden');
        }
      });
    });

    // Gestion affichage TD/bureau
    const typeDelegueRadios = document.querySelectorAll('input[name="typeDelegue"]');
    const groupeTD = document.getElementById('groupeTD');
    const bureauDelegue = document.getElementById('bureauDelegue');
    const bureauSelect = document.getElementById('bureauSelect');
    const autreFonctionDelegue = document.getElementById('autreFonctionDelegue');

    typeDelegueRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        if (radio.value === 'Groupe TD') {
          groupeTD.classList.remove('hidden');
          bureauDelegue.classList.add('hidden');
        } else {
          groupeTD.classList.add('hidden');
          bureauDelegue.classList.remove('hidden');
        }
      });
    });

    bureauSelect.addEventListener('change', () => {
      if (bureauSelect.value === 'Autre') {
        autreFonctionDelegue.classList.remove('hidden');
      } else {
        autreFonctionDelegue.classList.add('hidden');
      }
    });
  </script></body></html>
