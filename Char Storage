// Save character to localStorage
if (document.getElementById('oc-form')) {
  document.getElementById('oc-form').addEventListener('submit', function(e) {
    e.preventDefault();
    const name = document.getElementById('name').value;
    const bio = document.getElementById('bio').value;
    const ocs = JSON.parse(localStorage.getItem('ocs') || '[]');
    const id = Date.now().toString();
    ocs.push({ id, name, bio });
    localStorage.setItem('ocs', JSON.stringify(ocs));
    window.location.href = 'index.html';
  });
}

// Load list of OCs
if (document.getElementById('oc-list')) {
  const ocs = JSON.parse(localStorage.getItem('ocs') || '[]');
  const container = document.getElementById('oc-list');
  ocs.forEach(oc => {
    const div = document.createElement('div');
    div.innerHTML = `<a href="character.html?id=${oc.id}">${oc.name}</a>`;
    container.appendChild(div);
  });
}

// Load individual character
if (document.getElementById('character-profile')) {
  const params = new URLSearchParams(window.location.search);
  const id = params.get('id');
  const ocs = JSON.parse(localStorage.getItem('ocs') || '[]');
  const oc = ocs.find(c => c.id === id);
  if (oc) {
    document.getElementById('character-profile').innerHTML = `
      <h2>${oc.name}</h2>
      <p>${oc.bio}</p>
    `;
  } else {
    document.getElementById('character-profile').innerHTML = `<p>Character not found.</p>`;
  }
}
