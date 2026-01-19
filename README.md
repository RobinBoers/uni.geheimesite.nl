# 👋 Hallo studiegenoot

Dit is een kopie van mijn [originele site](//school.geheimesite.nl), maar dan voor Onderwijswetenschappen shtuff.

<form class="search-form">
  <label>
    Openen via de Universiteitsbibliotheek:
  </label>
  <input type="url" autofocus placeholder="https://doi.org/10.nnnnnn/example" required>
  <button type="button">Copy</button>
  <button type="submit">Open</button>
</form>

<script>
  function proxyURL(url) {
    const uri = new URL(url);
    const host = uri.hostname.replace(/\./g, '-') + '';
    return `https://${host}.utrechtuniversity.idm.oclc.org${uri.pathname}${uri.search}${uri.hash}`;
  }

  document.querySelector('form').onsubmit = (e) => {
    e.preventDefault();
    const url = document.querySelector('input').value;
    window.location.href = proxyURL(url);
  };

  document.querySelector('button[type="button"]').onclick = () => {
    const url = document.querySelector('input').value;
    navigator.clipboard.writeText(proxyURL(url)).then(() => (url.value = ''));
  };
</script>

## OWW1

- [Inleiding in de onderwijswetenschappen](/OWW1/IOWW/Samenvatting.md)
- [Kennismaking met onderzoeksmethoden en statistiek](/OWW1/KOM/Samenvatting.md)
- [Ontwerpen van leersituaties](/OWW1/OVL/Samenvatting.md)
- [Education & ICT](/OWW1/ICT/Samenvatting.md)
