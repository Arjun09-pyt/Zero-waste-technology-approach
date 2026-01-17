# Zero-waste-technology-approach
Zero Waste Technology – A Modern Approach is a BCA minor project focused on applying modern IT solutions to sustainable waste management. The project explores smart waste segregation, recycling methods, and technology-driven approaches using data analysis and automation to reduce environmental impact and promote zero-waste practices.
CODE FOR MY PROJECT:

<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Zero Waste Technology — A Modern Approach</title>
  <meta name="description" content="Zero Waste Technology: resources, gallery, upload images of waste and get a simple percentage breakdown." />

  <!-- Simple styling (responsive) -->
  <style>
    :root{--accent:#0ea5a4;--muted:#6b7280;--bg:#f8fafc}
    *{box-sizing:border-box}
    body{font-family:Inter,Segoe UI,system-ui,Roboto,Arial;margin:0;background:var(--bg);color:#0f172a}
    header{background:linear-gradient(90deg,#ecfeff,white);padding:28px 20px;border-bottom:1px solid #e6eef0}
    .wrap{max-width:1100px;margin:0 auto;padding:20px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(180deg,var(--accent),#0369a1);display:flex;align-items:center;justify-content:center;color:white;font-weight:700}
    h1{margin:0;font-size:1.6rem}
    p.lead{color:var(--muted);margin:8px 0 0}
    nav{margin-top:12px}
    nav a{margin-right:12px;color:var(--accent);text-decoration:none}

    .grid{display:grid;grid-template-columns:1fr;gap:20px;margin-top:20px}
    @media(min-width:900px){.grid{grid-template-columns:2fr 1fr}}

    .card{background:white;padding:18px;border-radius:12px;box-shadow:0 6px 18px rgba(2,6,23,0.06)}
    .section-title{display:flex;align-items:center;justify-content:space-between}
    .small{font-size:0.9rem;color:var(--muted)}

    /* Upload area */
    .upload{border:2px dashed #e6eef0;padding:18px;border-radius:10px;text-align:center;background:linear-gradient(180deg,rgba(14,165,164,0.03),transparent)}
    .upload input{display:none}
    .btn{display:inline-block;padding:10px 14px;border-radius:8px;background:var(--accent);color:white;text-decoration:none}

    /* Gallery */
    .gallery{display:flex;flex-wrap:wrap;gap:10px;margin-top:12px}
    .thumb{width:120px;height:80px;overflow:hidden;border-radius:8px;border:1px solid #e6eef0;display:flex;align-items:center;justify-content:center;background:#f8fafc}
    .results{display:flex;gap:10px;flex-wrap:wrap;margin-top:12px}
    .pill{background:#eefdfa;padding:6px 10px;border-radius:999px;border:1px solid #d1fbf8}

    footer{padding:20px;text-align:center;color:var(--muted);font-size:0.9rem}

    /* table */
    table{width:100%;border-collapse:collapse}
    th,td{padding:8px;border-bottom:1px solid #f1f5f9;text-align:left}
  </style>

  <!-- Chart.js (CDN) -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
</head>
<body>
  <header>
    <div class="wrap">
      <div class="brand">
        <div class="logo">ZW</div>
        <div>
          <h1>Zero Waste Technology — A Modern Approach</h1>
          <p class="lead">Learn methods, upload images of waste and get a quick breakdown — demo heuristics, gallery, resources and actionable steps.</p>
        </div>
      </div>
    </div>
  </header>

  <main class="wrap" role="main">
    <div class="grid">
      <section class="card">
        <div class="section-title">
          <h2>About this project</h2>
          <span class="small">Demo static site + lightweight image analysis</span>
        </div>
        <p>This website is a simple, educational site demonstrating zero waste technologies and workflows. It includes:
        </p>
        <ul>
          <li>Intro &amp; resources about zero waste technologies (composting, recycling, upcycling, product redesign)</li>
          <li>Image upload &amp; gallery so users can add photos of waste</li>
          <li>Client-side heuristic analysis that estimates percentage composition using color heuristics (toy demo — not production ML)</li>
          <li>Downloadable report (CSV) of results</li>
        </ul>

        <hr />
        <h3>How the image analyzer works (simple)</h3>
        <p class="small">The analyzer samples pixels from the uploaded image using an HTML canvas and classifies each sampled pixel into broad bins (organic, paper, plastic, metal/other) based on hue and brightness ranges. It returns approximate percentages and a small chart. This is a demonstration only — for real classification use a trained ML model or cloud API.</p>

        <hr />
        <div>
          <label class="upload" id="dropzone">
            <strong>Drop images here</strong><br>
            <em class="small">or</em>
            <br>
            <a class="btn" id="pick">Choose images</a>
            <input type="file" id="files" accept="image/*" multiple>
          </label>

          <div class="gallery" id="gallery" aria-live="polite" style="margin-top:12px"></div>

          <div class="results card" id="analysis" style="margin-top:12px;display:none">
            <div class="section-title"><h3>Image Analysis</h3><span class="small">Approximate composition</span></div>
            <canvas id="pie" style="max-width:300px;margin-top:12px"></canvas>
            <div id="legend" class="small" style="margin-top:8px"></div>
            <button id="downloadCSV" class="btn" style="margin-top:12px">Download CSV report</button>
          </div>
        </div>

      </section>

      <aside class="card">
        <h3>Quick Resources</h3>
        <table>
          <thead><tr><th>Topic</th><th>Action</th></tr></thead>
          <tbody>
            <tr><td>Composting</td><td>Home &amp; industrial compost systems</td></tr>
            <tr><td>Recycling</td><td>Clean, sorted streams &amp; design for disassembly</td></tr>
            <tr><td>Upcycling</td><td>Designs that give waste new value</td></tr>
            <tr><td>Policy</td><td>Deposit return schemes, EPR</td></tr>
          </tbody>
        </table>

        <hr />
        <h4>Notes</h4>
        <p class="small">This site is static and runs entirely in the browser. The image analysis is intentionally simple to keep it private — no images leave your machine.</p>
      </aside>
    </div>

    <section style="margin-top:20px">
      <div class="card">
        <h3>What you can do with this site</h3>
        <ol>
          <li>Upload photos of waste from your home or campus.</li>
          <li>See approximate composition percentages (demo only).</li>
          <li>Save the report as CSV and track improvements over time.</li>
          <li>Use resources &amp; calls-to-action to start local zero-waste programs.</li>
        </ol>
      </div>
    </section>

    <section class="wrap" style="margin-top:20px">
      <div class="card">
        <h2>Advanced Zero Waste Technologies</h2>
        <p>Below are some of the most modern and impactful technologies used in waste management, sorting, and resource recovery:</p>

        <h3>Waste Management and Sorting</h3>
        <ul>
          <li><strong>AI-powered trash sorters:</strong> Use artificial intelligence to automatically sort waste with high accuracy.</li>
          <li><strong>Smart recycling bins:</strong> Technology-enabled bins that guide users and improve collection efficiency.</li>
          <li><strong>Mixed waste processing:</strong> Involves shredding, bailing, and high-pressure heating to sanitize materials before advanced recovery.</li>
          <li><strong>Digital product passports:</strong> Provide transparent lifecycle and composition data to support reuse and recycling.</li>
        </ul>

        <h3>Resource Recovery and Conversion</h3>
        <ul>
          <li><strong>Waste-to-energy:</strong> Converts waste into usable energy through methane capture, gasification, or pyrolysis.</li>
          <li><strong>Advanced composting:</strong> Efficiently converts organic waste into nutrient-rich compost.</li>
          <li><strong>Biogas production:</strong> Uses organic waste to generate biogas for energy.</li>
          <li><strong>Nutrient recovery:</strong> Systems extract nitrogen, phosphorus, and other nutrients from wastewater.</li>
        </ul>
      </div>
    </section>

</main>

  <footer>
    <div class="wrap">Made with♻️ — Zero Waste Technology demo. Open-source, educational.</div>
  </footer>

  <!-- App JS -->
  <script>
    // Simple client-side heuristic classifier.
    // Bins: organic (green/brown), paper (light brown/white), plastic (bright colors incl. blue), metal/other (grey/dark)

    const filesEl = document.getElementById('files');
    const pick = document.getElementById('pick');
    const drop = document.getElementById('dropzone');
    const gallery = document.getElementById('gallery');
    const analysis = document.getElementById('analysis');
    const legend = document.getElementById('legend');
    const downloadCSV = document.getElementById('downloadCSV');

    pick.addEventListener('click',()=>filesEl.click());
    drop.addEventListener('dragover',e=>{e.preventDefault();drop.style.borderColor='var(--accent)'});
    drop.addEventListener('dragleave',()=>{drop.style.borderColor='#e6eef0'});
    drop.addEventListener('drop',e=>{e.preventDefault();drop.style.borderColor='#e6eef0';handleFiles(e.dataTransfer.files)});
    filesEl.addEventListener('change',e=>handleFiles(e.target.files));

    let resultsStore = [];
    let chart = null;

    function handleFiles(fileList){
      const files = Array.from(fileList).filter(f=>f.type.startsWith('image/'));
      if(!files.length) return;
      files.forEach(file=>{
        const url = URL.createObjectURL(file);
        const img = document.createElement('img');
        img.src = url; img.style.maxWidth='120px'; img.style.height='80px'; img.style.objectFit='cover'; img.className='thumbimg';
        const wrap = document.createElement('div'); wrap.className='thumb'; wrap.appendChild(img);
        gallery.prepend(wrap);

        img.onload = ()=>{
          analyzeImage(img,file.name);
          URL.revokeObjectURL(url);
        }
      })
    }

    function analyzeImage(img, name){
      // create canvas and sample
      const c = document.createElement('canvas');
      const ctx = c.getContext('2d');
      // downscale to speed
      const w = 200; const scale = w / img.naturalWidth;
      const h = Math.max(80, Math.floor(img.naturalHeight * scale));
      c.width = w; c.height = h;
      ctx.drawImage(img,0,0,w,h);
      const data = ctx.getImageData(0,0,w,h).data;
      const sampleStep = 6; // sample every Nth pixel
      const counts = {organic:0,paper:0,plastic:0,metal:0};
      let total = 0;
      for(let i=0;i<data.length;i += 4 * sampleStep){
        const r = data[i], g = data[i+1], b = data[i+2];
        total++;
        const hsl = rgbToHsl(r,g,b);
        const hdeg = hsl[0]*360; const s = hsl[1]; const l = hsl[2];
        // heuristics
        if(l < 0.12){ counts.metal++; continue } // very dark
        if(s < 0.08 && l>0.7){ counts.paper++; continue } // white-ish
        if(hdeg >= 40 && hdeg <= 120){ // green/yellow => organic
          counts.organic++; continue
        }
        if((hdeg>=180 && hdeg<=260) || s>0.45){ // blue-ish or high saturation => plastic (very approximate)
          counts.plastic++; continue
        }
        // fallback: paper or metal depending on lightness
        if(l > 0.5) counts.paper++; else counts.metal++;
      }

      const percentages = {
        organic: Math.round(100 * counts.organic/total),
        paper: Math.round(100 * counts.paper/total),
        plastic: Math.round(100 * counts.plastic/total),
        metal: Math.max(0, 100 - (Math.round(100 * (counts.organic+counts.paper+counts.plastic)/total)))
      };

      const entry = {name, time: new Date().toISOString(), percentages};
      resultsStore.push(entry);
      showResults(entry);
    }

    function showResults(entry){
      analysis.style.display='block';
      const data = entry.percentages;
      const labels = ['Organic','Paper','Plastic','Metal/Other'];
      const values = [data.organic,data.paper,data.plastic,data.metal];

      if(chart) chart.destroy();
      const ctx = document.getElementById('pie').getContext('2d');
      chart = new Chart(ctx,{
        type:'pie',
        data:{labels, datasets:[{data:values}]},
        options:{plugins:{legend:{display:false}}}
      });

      legend.innerHTML = '';
      labels.forEach((l,idx)=>{
        const v = values[idx];
        const el = document.createElement('div'); el.className='pill'; el.textContent = `${l}: ${v}%`;
        legend.appendChild(el);
      });
    }

    downloadCSV.addEventListener('click', ()=>{
      if(!resultsStore.length) return alert('No results yet');
      const rows = [];
      rows.push(['name','time','organic','paper','plastic','metal']);
      resultsStore.forEach(r=>{
        rows.push([r.name,r.time,r.percentages.organic,r.percentages.paper,r.percentages.plastic,r.percentages.metal]);
      });
      const csv = rows.map(r=>r.map(cell=>`"${String(cell).replace(/"/g,'""')}"`).join(',')).join('\n');
      const blob = new Blob([csv],{type:'text/csv'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href=url; a.download='zero-waste-report.csv'; a.click();
      URL.revokeObjectURL(url);
    });

    // small helper: convert rgb to hsl; returns [h,s,l] with h in [0,1]
    function rgbToHsl(r,g,b){
      r/=255; g/=255; b/=255; const max=Math.max(r,g,b), min=Math.min(r,g,b);
      let h=0,s=0,l=(max+min)/2;
      if(max!==min){ const d=max-min; s = l>0.5? d/(2-max-min): d/(max+min);
        switch(max){case r: h=(g-b)/d + (g<b?6:0); break; case g: h=(b-r)/d + 2; break; case b: h=(r-g)/d + 4; break}
        h/=6;
      }
      return [h,s,l];
    }

  </script>
</body>
</html>
