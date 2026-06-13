# 👋 Hallo studiegenoot

Dit is een kopie van mijn [originele site](//school.geheimesite.nl), maar dan voor Onderwijswetenschappen shtuff.

<form class="search-form">
  <label>
    Openen via de Universiteitsbibliotheek:
  </label>
  <input type="url" autofocus placeholder="https://doi.org/10.nnnnnn/example" required>
  <button type="button" id="copy">Copy</button>
  <button type="button" id="cite">Cite</button>
  <button type="submit">Open</button>
</form>

<script>
  function proxyURL(url) {
    const uri = new URL(url);
    const host = uri.hostname.replace(/\./g, '-') + '';
    return `https://${host}.utrechtuniversity.idm.oclc.org${uri.pathname}${uri.search}${uri.hash}`;
  }

  async function citeURL(url) {
    const doi = extractDOI(url) || await findDOI(url);
    if (!doi) return alert('Could not find DOI on target page.');

    const data = await fetchCrossref(doi);

    return formatAPA(data, doi);
  }

  function extractDOI(input) {
    const match = input.match(/10\.\d{4,9}\/[-._;()/:A-Z0-9]+/i);
    return match ? match[0].replace(/["'<>\s]/g, '') : null;
  }

  async function findDOI(url) {
    const html = await fetchPage(url);
    return extractDOI(html);
  }

  async function fetchPage(url) {
    const res = await fetch(`https://api.allorigins.win/raw?url=${encodeURIComponent(url)}`);
    return await res.text();
  }

  async function fetchCrossref(doi) {
    const res = await fetch(`https://api.crossref.org/works/${doi}`);
    const data = await res.json();
    return data.message;
  }

  function formatAPA(data, doi) {
    const Cite = require('citation-js');
    const cite = new Cite(data);
    return cite.format('bibliography', {
      format: 'text',
      template: 'apa',
      lang: 'en-US'
    });

    const authors = data.author?.map(a => `${a.family}, ${a.given?.[0] || ''}.`).join(', ') || '';

    const year = data.issued?.['date-parts']?.[0]?.[0] || 'n.d.';
    const title = data.title?.[0] || '';
    const journal = data['container-title']?.[0] || '';

    return `${authors} (${year}). ${title}. ${journal}. https://doi.org/${doi}`;
  }

  document.querySelector('form').onsubmit = (e) => {
    e.preventDefault();
    const url = document.querySelector('input').value;
    window.location.href = proxyURL(url);
  };

  document.getElementById("copy").onclick = (e) => {
    const text = e.target.innerText;
    const url = document.querySelector('input');
    const proxied = proxyURL(url.value);
    navigator.clipboard.writeText(proxied).then(() => (url.value = ''));
    e.target.innerText = "copied!";
    setTimeout(() => (e.target.innerText = text), 2000);
  };

  document.getElementById("cite").onclick = async (e) => {
    const text = e.target.innerText;
    const url = document.querySelector('input');
    e.target.innerText = "fetching...";
    const citation = await citeURL(url.value);
    if(!citation) return;
    navigator.clipboard.writeText(citation).then(() => (url.value = ''));
    e.target.innerText = "copied!";
    setTimeout(() => (e.target.innerText = text), 2000);
  };
</script>

<style>
  input:user-invalid {
    border-color: inherit;
  }
</style>

## OWW1

- [Inleiding in de onderwijswetenschappen](/OWW1/IOWW/Samenvatting.md)
- [Kennismaking met onderzoeksmethoden en statistiek](/OWW1/KOM/Samenvatting.md)
- [Ontwerpen van leersituaties](/OWW1/OVL/Samenvatting.md)
- [Education & ICT](/OWW1/EICT/Samenvatting.md)
- [Wetenschapsfilosofie en onderwijsgeschiedenis](/OWW1/WETFIL/Samenvatting.md)
