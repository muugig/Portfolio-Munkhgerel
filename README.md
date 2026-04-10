# index.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Munkhgerel Ankhtuvshin — Portfolio</title>
  <style>
    *{margin:0;padding:0;box-sizing:border-box;}
    :root{
      --dark:   #1e2533;
      --darker: #161b27;
      --gold:   #c9a84c;
      --gold2:  #e8c96d;
      --text:   #1e2533;
      --grey:   #5a6475;
      --light:  #f7f8fa;
      --white:  #ffffff;
      --border: #e4e8f0;
      --card:   #ffffff;
    }
    html{scroll-behavior:smooth;}
    body{font-family:'Segoe UI',Calibri,sans-serif;background:var(--light);color:var(--text);line-height:1.7;}

    /* NAV */
    nav{
      position:fixed;top:0;width:100%;z-index:100;
      background:var(--darker);
      display:flex;justify-content:space-between;align-items:center;
      padding:0 2.5rem;height:56px;
      box-shadow:0 2px 16px rgba(0,0,0,0.25);
    }
    nav .logo{color:var(--gold);font-weight:700;font-size:1rem;letter-spacing:.5px;}
    nav ul{list-style:none;display:flex;gap:1.8rem;}
    nav ul li a{color:#ccd2de;text-decoration:none;font-size:.86rem;letter-spacing:.3px;transition:color .2s;}
    nav ul li a:hover{color:var(--gold);}

    /* HERO */
    #hero{
      background: linear-gradient(135deg, #1e2533 0%, #2c3547 60%, #1e2533 100%);
      min-height:100vh;display:flex;align-items:center;justify-content:center;
      text-align:center;padding:7rem 1.5rem 5rem;
      position:relative;overflow:hidden;
    }
    #hero::before{
      content:'';position:absolute;inset:0;
      background: radial-gradient(ellipse at 70% 40%, rgba(201,168,76,0.08) 0%, transparent 65%);
    }
    #hero .avatar{
      width:115px;height:115px;border-radius:50%;
      background:linear-gradient(135deg, var(--gold), var(--gold2));
      display:flex;align-items:center;justify-content:center;
      font-size:2.6rem;font-weight:700;color:var(--darker);
      margin:0 auto 1.5rem;
      box-shadow:0 0 0 6px rgba(201,168,76,0.2);
    }
    #hero h1{color:var(--white);font-size:2.5rem;font-weight:700;margin-bottom:.4rem;letter-spacing:-.3px;}
    #hero .tagline{color:var(--gold2);font-size:1rem;margin-bottom:1.8rem;letter-spacing:.5px;}
    #hero .contact-bar{display:flex;flex-wrap:wrap;justify-content:center;gap:.7rem;margin-bottom:2rem;}
    #hero .contact-bar a{
      color:#ccd2de;text-decoration:none;font-size:.85rem;
      background:rgba(255,255,255,0.07);padding:.35rem .9rem;
      border-radius:20px;border:1px solid rgba(255,255,255,0.13);
      transition:all .2s;
    }
    #hero .contact-bar a:hover{background:rgba(201,168,76,0.15);border-color:var(--gold);color:var(--gold);}
    #hero .badges{display:flex;flex-wrap:wrap;justify-content:center;gap:.55rem;}
    #hero .badge{
      background:rgba(201,168,76,0.12);color:var(--gold2);
      border:1px solid rgba(201,168,76,0.3);
      padding:.28rem .8rem;border-radius:20px;font-size:.8rem;
    }

    /* SECTIONS */
    section{padding:5rem 1.5rem;}
    section:nth-child(even){background:var(--white);}
    .container{max-width:880px;margin:0 auto;}
    .section-title{font-size:1.5rem;font-weight:700;color:var(--text);margin-bottom:.4rem;}
    .section-divider{width:40px;height:3px;background:var(--gold);border-radius:2px;margin-bottom:2.5rem;}

    /* ABOUT */
    .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:2rem;}
    .about-text p{font-size:.97rem;color:var(--grey);margin-bottom:.9rem;}
    .about-highlights{display:flex;flex-direction:column;gap:.8rem;}
    .highlight-item{
      background:var(--light);border:1px solid var(--border);border-radius:10px;
      padding:.9rem 1.1rem;display:flex;align-items:flex-start;gap:.7rem;
      border-left:3px solid var(--gold);
    }
    .highlight-item .hi{font-size:1.2rem;}
    .highlight-item p{font-size:.88rem;color:var(--grey);}
    .highlight-item strong{display:block;font-size:.9rem;color:var(--text);margin-bottom:.1rem;}

    /* TOOLS */
    .tools-grid{display:flex;flex-wrap:wrap;gap:.75rem;}
    .tool-tag{
      background:var(--card);border:1px solid var(--border);
      border-radius:8px;padding:.5rem 1rem;
      font-size:.88rem;color:var(--text);font-weight:500;
      display:flex;align-items:center;gap:.4rem;
      box-shadow:0 1px 4px rgba(0,0,0,0.05);
      transition:border-color .2s, box-shadow .2s;
    }
    .tool-tag:hover{border-color:var(--gold);box-shadow:0 2px 8px rgba(201,168,76,0.15);}
    .tool-tag .dot{width:8px;height:8px;border-radius:50%;background:var(--gold);flex-shrink:0;}

    /* PROJECTS */
    .projects-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem;}
    .project-card{
      background:var(--card);border:1px solid var(--border);
      border-radius:12px;padding:1.4rem 1.5rem;
      box-shadow:0 1px 4px rgba(0,0,0,0.05);
      transition:box-shadow .2s, transform .2s;
      display:flex;flex-direction:column;gap:.8rem;
    }
    .project-card:hover{box-shadow:0 6px 20px rgba(0,0,0,0.1);transform:translateY(-2px);}
    .project-card .proj-header{display:flex;align-items:center;gap:.8rem;}
    .project-card .proj-icon{
      width:42px;height:42px;border-radius:10px;
      background:var(--darker);color:var(--gold);
      display:flex;align-items:center;justify-content:center;
      font-size:1.3rem;flex-shrink:0;
    }
    .project-card h3{font-size:1rem;font-weight:700;color:var(--text);}
    .project-card .proj-desc{font-size:.88rem;color:var(--grey);line-height:1.6;}
    .project-card .proj-tags{display:flex;flex-wrap:wrap;gap:.4rem;}
    .project-card .tag{
      background:var(--light);border:1px solid var(--border);
      border-radius:6px;padding:.18rem .6rem;
      font-size:.75rem;color:var(--grey);font-weight:500;
    }
    .project-card .proj-link{
      display:inline-flex;align-items:center;gap:.4rem;
      color:var(--gold);text-decoration:none;font-size:.85rem;font-weight:600;
      margin-top:auto;transition:opacity .2s;
    }
    .project-card .proj-link:hover{opacity:.75;}

    /* SKILLS */
    .skills-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
    .skill-card{
      background:var(--card);border:1px solid var(--border);
      border-radius:10px;padding:1rem 1.2rem;
      display:flex;align-items:flex-start;gap:.75rem;
      box-shadow:0 1px 4px rgba(0,0,0,0.04);
      transition:box-shadow .2s;
    }
    .skill-card:hover{box-shadow:0 4px 14px rgba(0,0,0,0.09);}
    .skill-card .icon{
      width:38px;height:38px;border-radius:9px;
      background:var(--darker);color:var(--gold);
      display:flex;align-items:center;justify-content:center;
      font-size:1.05rem;flex-shrink:0;
    }
    .skill-card h4{font-size:.88rem;font-weight:600;color:var(--text);margin-bottom:.2rem;}
    .skill-card p{font-size:.81rem;color:var(--grey);}

    /* EXPERIENCE */
    .timeline{position:relative;padding-left:1.8rem;}
    .timeline::before{content:'';position:absolute;left:6px;top:6px;bottom:6px;width:2px;background:var(--border);}
    .timeline-item{position:relative;margin-bottom:2.4rem;}
    .timeline-item::before{
      content:'';position:absolute;left:-1.8rem;top:6px;
      width:14px;height:14px;border-radius:50%;
      background:var(--gold);border:3px solid var(--white);
      box-shadow:0 0 0 2px var(--gold);
    }
    .timeline-item .dates{font-size:.78rem;color:var(--gold);font-weight:600;letter-spacing:.4px;margin-bottom:.3rem;text-transform:uppercase;}
    .timeline-item h3{font-size:1.05rem;font-weight:700;color:var(--text);}
    .timeline-item .org{font-size:.88rem;color:var(--grey);margin-bottom:.7rem;}
    .timeline-item ul{padding-left:1.1rem;}
    .timeline-item ul li{font-size:.91rem;color:var(--grey);margin-bottom:.35rem;}

    /* EDUCATION */
    .edu-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem;}
    .edu-card{
      background:var(--card);border:1px solid var(--border);
      border-radius:10px;padding:1.3rem 1.4rem;
      border-top:3px solid var(--gold);
      box-shadow:0 1px 4px rgba(0,0,0,0.04);
    }
    .edu-card .year{font-size:.76rem;color:var(--gold);font-weight:600;margin-bottom:.4rem;text-transform:uppercase;letter-spacing:.4px;}
    .edu-card h3{font-size:.98rem;font-weight:700;color:var(--text);margin-bottom:.25rem;}
    .edu-card p{font-size:.84rem;color:var(--grey);}
    .edu-card .modules{margin-top:.5rem;font-size:.78rem;color:#8a94a6;}

    /* CERTIFICATIONS */
    .cert-list{display:flex;flex-direction:column;gap:.9rem;}
    .cert-item{
      background:var(--card);border:1px solid var(--border);
      border-radius:10px;padding:1rem 1.3rem;
      display:flex;align-items:center;justify-content:space-between;gap:1rem;
      box-shadow:0 1px 4px rgba(0,0,0,0.04);
    }
    .cert-item h4{font-size:.94rem;font-weight:600;color:var(--text);}
    .cert-item p{font-size:.81rem;color:var(--grey);margin-top:.15rem;}
    .cert-badge{font-size:.74rem;font-weight:600;padding:.25rem .8rem;border-radius:20px;white-space:nowrap;flex-shrink:0;}
    .cert-badge.progress{background:#fef9ec;color:#92680a;border:1px solid var(--gold);}
    .cert-badge.done{background:#edfbf3;color:#0a6640;border:1px solid #7fcca6;}

    /* PERSONAL */
    .personal-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
    .personal-card{
      background:var(--card);border:1px solid var(--border);
      border-radius:10px;padding:1.1rem 1.3rem;
      display:flex;align-items:flex-start;gap:.8rem;
      box-shadow:0 1px 4px rgba(0,0,0,0.04);
    }
    .personal-card .emoji{font-size:1.5rem;flex-shrink:0;}
    .personal-card h4{font-size:.9rem;font-weight:600;color:var(--text);margin-bottom:.2rem;}
    .personal-card p{font-size:.83rem;color:var(--grey);}

    /* LANGUAGES */
    .lang-grid{display:flex;gap:1rem;flex-wrap:wrap;}
    .lang-card{
      background:var(--card);border:1px solid var(--border);
      border-radius:10px;padding:1rem 1.6rem;text-align:center;min-width:145px;
      box-shadow:0 1px 4px rgba(0,0,0,0.04);
    }
    .lang-card h4{font-size:1rem;font-weight:700;color:var(--text);}
    .lang-card p{font-size:.82rem;color:var(--grey);margin-top:.2rem;}
    .lang-bar{height:5px;border-radius:3px;background:var(--border);margin-top:.7rem;}
    .lang-bar .fill{height:100%;border-radius:3px;background:linear-gradient(90deg,var(--gold),var(--gold2));}

    /* CONTACT */
    .contact-btns{display:flex;flex-wrap:wrap;gap:.9rem;margin-top:1.5rem;}
    .contact-btns a{
      display:flex;align-items:center;gap:.5rem;
      padding:.7rem 1.3rem;border-radius:8px;
      text-decoration:none;font-size:.9rem;font-weight:500;
      transition:opacity .2s;
    }
    .contact-btns a:hover{opacity:.85;}
    .btn-dark{background:var(--darker);color:var(--white);}
    .btn-gold{background:var(--gold);color:var(--darker);}
    .btn-li{background:#0077b5;color:#fff;}
    .btn-gh{background:#24292e;color:#fff;}

    /* FOOTER */
    footer{
      background:var(--darker);color:#8a94a6;
      text-align:center;padding:2rem 1.5rem;font-size:.83rem;
    }
    footer a{color:var(--gold);text-decoration:none;}

    @media(max-width:640px){
      .skills-grid,.edu-grid,.personal-grid,.about-grid,.projects-grid{grid-template-columns:1fr;}
      #hero h1{font-size:1.85rem;}
      nav ul{gap:.9rem;}
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Munkhgerel A.</div>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#personal">Personal</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div style="position:relative;z-index:1;">
    <div class="avatar">MA</div>
    <h1>Munkhgerel Ankhtuvshin</h1>
    <p class="tagline">ACCA Student &nbsp;·&nbsp; Accountant &nbsp;·&nbsp; Data Analytics Graduate</p>
    <div class="contact-bar">
      <a href="tel:+353830085046">📞 +353 83 008 50 46</a>
      <a href="mailto:ankhtuvshinmunkhgerel@gmail.com">✉️ ankhtuvshinmunkhgerel@gmail.com</a>
      <a href="https://www.linkedin.com/in/munkhgerel-ankhtuvshin-983839183/" target="_blank">🔗 LinkedIn</a>
      <a href="https://github.com/muugig" target="_blank">💻 GitHub</a>
      <a>📍 Dublin, Ireland</a>
    </div>
    <div class="badges">
      <span class="badge">BSc Accountancy</span>
      <span class="badge">MSc Data Analytics</span>
      <span class="badge">ACCA (PM) In Progress</span>
      <span class="badge">Google Analytics Certified</span>
      <span class="badge">Eligible to Work in Ireland</span>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="section-title">About Me</div>
    <div class="section-divider"></div>
    <div class="about-grid">
      <div class="about-text">
        <p>I am a finance and analytics professional based in Dublin, Ireland, with a BSc in Accountancy and an MSc in Data Analytics from CCT College Dublin. I bring hands-on experience in financial reporting, accounts receivable, ERP implementation, VAT compliance, and cost control, gained at MCS Coca-Cola LLC.</p>
        <p>I am currently pursuing the ACCA qualification (Performance Management) and hold a Google Data Analytics Certificate. I combine strong commercial acumen with advanced data skills — Python, SQL, Power BI, and Tableau — to deliver accurate, insight-driven analysis.</p>
        <p>I am actively seeking opportunities in accounting, finance, bookkeeping, or quantity surveying where I can apply my skills and grow long-term.</p>
      </div>
      <div class="about-highlights">
        <div class="highlight-item">
          <div class="hi">🎯</div>
          <div><strong>Career Goal</strong><p>To build a long-term career in accounting or finance, growing through hands-on experience and professional qualifications like ACCA.</p></div>
        </div>
        <div class="highlight-item">
          <div class="hi">🏆</div>
          <div><strong>My Journey</strong><p>Moved to Dublin, Ireland to pursue a Master's degree and professional qualifications — driven by a genuine passion for finance and a belief that growth happens when you push yourself outside your comfort zone.</p></div>
        </div>
        <div class="highlight-item">
          <div class="hi">📍</div>
          <div><strong>Location & Availability</strong><p>Based in Dublin, Ireland. Fully eligible to work. Available immediately.</p></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="section-title">Projects</div>
    <div class="section-divider"></div>
    <div class="projects-grid">

      <div class="project-card">
        <div class="proj-header">
          <div class="proj-icon">📈</div>
          <h3>Stock Prediction Models</h3>
        </div>
        <p class="proj-desc">
          A machine learning project that builds and compares multiple predictive models to forecast stock market prices. Explores time-series analysis, regression techniques, and data preprocessing pipelines to identify patterns in historical financial data and generate forward-looking price predictions.
        </p>
        <div class="proj-tags">
          <span class="tag">Python</span>
          <span class="tag">Machine Learning</span>
          <span class="tag">Time-Series</span>
          <span class="tag">Data Analysis</span>
          <span class="tag">Financial Data</span>
        </div>
        <a class="proj-link" href="https://github.com/muugig/Stock-Prediction-Models" target="_blank">
          💻 View on GitHub →
        </a>
      </div>

      <div class="project-card">
        <div class="proj-header">
          <div class="proj-icon">😷</div>
          <h3>Face Mask Detection</h3>
        </div>
        <p class="proj-desc">
          A computer vision project using deep learning to detect whether individuals are wearing face masks in real time. Built using image classification techniques and neural networks, this project was developed in the context of COVID-19 public health monitoring and demonstrates practical AI applied to a real-world problem.
        </p>
        <div class="proj-tags">
          <span class="tag">Python</span>
          <span class="tag">Deep Learning</span>
          <span class="tag">Computer Vision</span>
          <span class="tag">Neural Networks</span>
          <span class="tag">Image Classification</span>
        </div>
        <a class="proj-link" href="https://github.com/muugig/Face-Mask-Detection" target="_blank">
          💻 View on GitHub →
        </a>
      </div>

    </div>
  </div>
</section>

<!-- TOOLS -->
<section id="tools">
  <div class="container">
    <div class="section-title">Tools & Technologies</div>
    <div class="section-divider"></div>
    <div class="tools-grid">
      <div class="tool-tag"><span class="dot"></span>Microsoft Excel</div>
      <div class="tool-tag"><span class="dot"></span>Power BI</div>
      <div class="tool-tag"><span class="dot"></span>Python</div>
      <div class="tool-tag"><span class="dot"></span>SQL</div>
      <div class="tool-tag"><span class="dot"></span>Tableau</div>
      <div class="tool-tag"><span class="dot"></span>Hadoop</div>
      <div class="tool-tag"><span class="dot"></span>Microsoft Word</div>
      <div class="tool-tag"><span class="dot"></span>Microsoft Outlook</div>
      <div class="tool-tag"><span class="dot"></span>ERP Systems</div>
      <div class="tool-tag"><span class="dot"></span>Microsoft PowerPoint</div>
      <div class="tool-tag"><span class="dot"></span>Google Analytics</div>
      <div class="tool-tag"><span class="dot"></span>Bright Manager (Learning)</div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="section-title">Key Skills</div>
    <div class="section-divider"></div>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="icon">💰</div>
        <div><h4>Financial Reporting & Analysis</h4><p>Preparing accurate financial reports, cost analysis, and insight-driven summaries for decision-making.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">📋</div>
        <div><h4>Accounts Receivable & Credit Control</h4><p>Managing debtor ledgers, reconciling accounts, chasing overdue payments, and resolving billing queries.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">📊</div>
        <div><h4>Data Analysis & Visualisation</h4><p>Python, SQL, Excel, Power BI, and Tableau for data-driven insights and clear visual reporting.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">🧾</div>
        <div><h4>VAT Compliance & Tax Reporting</h4><p>Preparing and submitting VAT reports in full compliance with statutory regulatory requirements.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">⚙️</div>
        <div><h4>ERP Systems & Data Management</h4><p>Hands-on experience implementing and operating ERP systems to streamline accounting processes.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">🔍</div>
        <div><h4>Audit & Internal Controls</h4><p>Conducting cash audits, verifying transactions, and safeguarding financial integrity.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">🤝</div>
        <div><h4>Client Communication & Service</h4><p>Professional client-facing experience across hospitality, corporate, and government environments.</p></div>
      </div>
      <div class="skill-card">
        <div class="icon">📦</div>
        <div><h4>Procurement & Cost Control</h4><p>Supporting procurement processes, managing supplier accounts, and monitoring project budgets.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="container">
    <div class="section-title">Work Experience</div>
    <div class="section-divider"></div>
    <div class="timeline">

      <div class="timeline-item">
        <div class="dates">Apr 2020 – Apr 2022</div>
        <h3>Customs Officer</h3>
        <div class="org">Chinggis Khaan International Airport &nbsp;·&nbsp; Ulaanbaatar, Mongolia</div>
        <ul>
          <li>Conducted customs inspections and enforced airport security protocols in a high-pressure environment, including through the COVID-19 pandemic.</li>
          <li>Played a pivotal role in identifying and seizing the largest gold-smuggling attempt in the airport's history.</li>
          <li>Investigated and documented smuggling methods, resulting in enhanced customs procedures and security measures.</li>
          <li>Collaborated with government agencies using intelligence data to identify threats and ensure full regulatory compliance.</li>
        </ul>
      </div>

      <div class="timeline-item">
        <div class="dates">Oct 2019 – Apr 2020</div>
        <h3>Accountant</h3>
        <div class="org">MCS Coca-Cola LLC &nbsp;·&nbsp; Ulaanbaatar, Mongolia</div>
        <ul>
          <li>Contributed to the successful ERP system implementation, streamlining accounting workflows and improving data accuracy.</li>
          <li>Monitored and verified daily sales transactions from distributor networks, ensuring accurate and timely data entry.</li>
          <li>Reconciled and closed accounts receivable for distributor clients, maintaining up-to-date ledger records.</li>
          <li>Prepared and submitted VAT reports in full compliance with statutory regulatory requirements.</li>
          <li>Oversaw cash transactions, conducted regular audits, and performed cash-count checks to safeguard financial integrity.</li>
        </ul>
      </div>

      <div class="timeline-item">
        <div class="dates">Previous Experience</div>
        <h3>Waitress</h3>
        <div class="org">Restaurant &nbsp;·&nbsp; Hospitality Sector</div>
        <ul>
          <li>Delivered a high standard of customer service in a fast-paced, client-facing environment, managing multiple tables and priorities simultaneously.</li>
          <li>Developed the ability to read people quickly and adapt communication style to suit all types of customers — from diffusing complaints to building instant rapport.</li>
          <li>Maintained sharp attention to detail with every order, ensuring accuracy and presentation met the highest standards.</li>
          <li>Demonstrated professionalism, friendliness, and composure under pressure at all times.</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="container">
    <div class="section-title">Education</div>
    <div class="section-divider"></div>
    <div class="edu-grid">
      <div class="edu-card">
        <div class="year">Graduation 2025 · Dublin, Ireland</div>
        <h3>MSc in Data Analytics</h3>
        <p>CCT College Dublin</p>
        <p class="modules">Machine Learning · Big Data · Data Visualisation · Business Intelligence</p>
      </div>
      <div class="edu-card">
        <div class="year">Graduation 2019 · Ulaanbaatar, Mongolia</div>
        <h3>BSc in Accountancy</h3>
        <p>University of Finance and Economics</p>
        <p class="modules">Cost Accounting · Financial Management · Auditing · Business Law · Economics</p>
      </div>
    </div>

    <br>
    <div class="section-title" style="font-size:1.15rem;margin-top:1.5rem;">Certifications</div>
    <div class="section-divider" style="margin-bottom:1.3rem;"></div>
    <div class="cert-list">
      <div class="cert-item">
        <div>
          <h4>ACCA – Performance Management (PM)</h4>
          <p>Association of Chartered Certified Accountants &nbsp;·&nbsp; Currently studying</p>
        </div>
        <span class="cert-badge progress">In Progress</span>
      </div>
      <div class="cert-item">
        <div>
          <h4>Google Data Analytics Professional Certificate</h4>
          <p>Coursera / Google</p>
        </div>
        <span class="cert-badge done">Completed ✓</span>
      </div>
    </div>

    <br>
    <div class="section-title" style="font-size:1.15rem;margin-top:1.5rem;">ACCA Exemptions Awarded</div>
    <div class="section-divider" style="margin-bottom:1rem;"></div>
    <p style="color:var(--grey);font-size:.88rem;margin-bottom:1.1rem;">
      Awarded 4 ACCA exemptions based on my BSc in Accountancy — recognising the academic foundation already achieved.
    </p>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:.75rem;">
      <div style="background:var(--light);border:1px solid var(--border);border-radius:9px;padding:.85rem 1.1rem;display:flex;align-items:center;gap:.8rem;">
        <span style="font-size:1.1rem;">✅</span>
        <div>
          <div style="font-size:.88rem;font-weight:600;color:var(--text);">Business and Technology (BT)</div>
          <div style="font-size:.76rem;color:var(--grey);">ACCA Exemption Granted</div>
        </div>
      </div>
      <div style="background:var(--light);border:1px solid var(--border);border-radius:9px;padding:.85rem 1.1rem;display:flex;align-items:center;gap:.8rem;">
        <span style="font-size:1.1rem;">✅</span>
        <div>
          <div style="font-size:.88rem;font-weight:600;color:var(--text);">Financial Accounting (FA)</div>
          <div style="font-size:.76rem;color:var(--grey);">ACCA Exemption Granted</div>
        </div>
      </div>
      <div style="background:var(--light);border:1px solid var(--border);border-radius:9px;padding:.85rem 1.1rem;display:flex;align-items:center;gap:.8rem;">
        <span style="font-size:1.1rem;">✅</span>
        <div>
          <div style="font-size:.88rem;font-Weight:600;color:var(--text);">Corporate and Business Law (LW)</div>
          <div style="font-size:.76rem;color:var(--grey);">ACCA Exemption Granted</div>
        </div>
      </div>
      <div style="background:var(--light);border:1px solid var(--border);border-radius:9px;padding:.85rem 1.1rem;display:flex;align-items:center;gap:.8rem;">
        <span style="font-size:1.1rem;">✅</span>
        <div>
          <div style="font-size:.88rem;font-weight:600;color:var(--text);">Management Accounting (MA)</div>
          <div style="font-size:.76rem;color:var(--grey);">ACCA Exemption Granted</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PERSONAL -->
<section id="personal">
  <div class="container">
    <div class="section-title">Personal Qualities</div>
    <div class="section-divider"></div>
    <p style="color:var(--grey);font-size:.95rem;margin-bottom:1.8rem;">
      Beyond the qualifications and experience, here's what I bring as a person.
    </p>
    <div class="personal-grid">
      <div class="personal-card">
        <div class="emoji">🗣️</div>
        <div><h4>Natural Communicator</h4><p>Years of working directly with people in hospitality and corporate environments have given me a confident, warm, and professional communication style that works with anyone.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">🔎</div>
        <div><h4>Detail-Oriented</h4><p>I genuinely love getting things right. Whether it's a financial report, a customer order, or a formatted document — I notice the details others miss and take pride in accuracy.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">🔄</div>
        <div><h4>Adaptable & Open to Change</h4><p>I embrace new situations, environments, and ways of doing things with a positive attitude. I find it easy to adjust when things shift — whether it's a new role, a new system, or a new challenge — and I see change as an opportunity to grow rather than something to resist.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">✨</div>
        <div><h4>Love for Organisation & Aesthetics</h4><p>I care deeply about how things look and feel. I love creating well-structured, visually clean work — from spreadsheets to documents to physical spaces.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">🙋</div>
        <div><h4>Curious & Not Afraid to Ask</h4><p>I'm not shy about asking questions when I need clarity — but I know when to step back. I believe asking the right questions at the right time is a strength, not a weakness.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">🤲</div>
        <div><h4>Hands-On & Creative</h4><p>I love making things — whether that's building something by hand, crafting a solution, or designing something from scratch. I bring energy and care to everything I create.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">🌍</div>
        <div><h4>Culturally Aware & Adaptable</h4><p>Having lived and worked across different countries and cultures, I connect easily with people from all walks of life. I bring an open mind and genuine curiosity to every environment.</p></div>
      </div>
      <div class="personal-card">
        <div class="emoji">🤝</div>
        <div><h4>Friendly with Clear Boundaries</h4><p>I'm warm, approachable, and easy to work with — while also maintaining professionalism and knowing where the line is. Colleagues and clients always feel comfortable around me.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- LANGUAGES -->
<section id="languages">
  <div class="container">
    <div class="section-title">Languages</div>
    <div class="section-divider"></div>
    <div class="lang-grid">
      <div class="lang-card">
        <h4>🇲🇳 Mongolian</h4>
        <p>Native</p>
        <div class="lang-bar"><div class="fill" style="width:100%"></div></div>
      </div>
      <div class="lang-card">
        <h4>🇷🇺 Russian</h4>
        <p>Advanced</p>
        <div class="lang-bar"><div class="fill" style="width:85%"></div></div>
      </div>
      <div class="lang-card">
        <h4>🇮🇪 English</h4>
        <p>Fluent / Professional</p>
        <div class="lang-bar"><div class="fill" style="width:82%"></div></div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="section-title">Get In Touch</div>
    <div class="section-divider"></div>
    <p style="color:var(--grey);font-size:.97rem;max-width:600px;">
      I am currently open to opportunities in accounting, finance, bookkeeping, credit control, and quantity surveying across Ireland. Feel free to reach out — I would love to hear from you!
    </p>
    <div class="contact-btns">
      <a href="tel:+353830085046" class="btn-dark">📞 +353 83 008 50 46</a>
      <a href="mailto:ankhtuvshinmunkhgerel@gmail.com" class="btn-gold">✉️ Email Me</a>
      <a href="https://www.linkedin.com/in/munkhgerel-ankhtuvshin-983839183/" target="_blank" class="btn-li">🔗 LinkedIn</a>
      <a href="https://github.com/muugig" target="_blank" class="btn-gh">💻 GitHub</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2026 Munkhgerel Ankhtuvshin &nbsp;·&nbsp; Dublin, Ireland &nbsp;·&nbsp;
    <a href="mailto:ankhtuvshinmunkhgerel@gmail.com">ankhtuvshinmunkhgerel@gmail.com</a>
  </p>
</footer>

</body>
</html>
