---
title: "Curriculum Vitae"
---


## Personal Details
**Name:** Mr. Nipul Gordhanbhai Shihora  
**Date of Birth:** October 8, 1989  
**Email:** [nipul@iiti.ac.in](mailto:nipul@iiti.ac.in), [nipulgs@gmail.com](mailto:nipulgs@gmail.com)  
**Phone:** +91-97229-54642  
**ORCID:** [0000-0002-4480-388X](https://orcid.org/0000-0002-4480-388X)  
**Languages Known:** Gujarati, Hindi, English.

---

## Professional Summary
Library and Information Science professional with over a decade of experience across premier institutions like IIT Indore, INFLIBNET Centre, IIT Bhubaneswar, and IIT Gandhinagar. Proficient in digital library systems, e-resource management, RFID technologies, institutional repositories, scholarly communication, and web-based library services.

---

## Educational Qualifications

| Degree | Institution | Year | Grade |
|--------|-------------|------|-------|
| M.LISc | Sardar Patel University | 2013 | First Class |
| B.LISc | Sardar Patel University | 2012 | First Class |
| B.Com | Saurashtra University | 2011 | Second Class |
| HSC | GSHSEB Gandhinagar | 2008 | Second Class |
| SSC | GSHSEB Gandhinagar | 2006 | Second Class |

---

## Certifications
- UGC-NET Qualified (July 2018 & July 2019)

---

## Professional Experience
**Total Professional Experience:**  
<span id="totalExperience"></span>

## Indian Institute of Technology Indore
**Designation:** Library Information Assistant

**Duration:** <span class="exp-duration"
      data-start="2021-06-01"
      data-end="present">
</span>

**Key Responsibilities:**
- Maintain LRC IT infrastructure, DSpace, Koha, Library Website, and LibDDS Portal
- Manage e-resources, access authentication, and vendor liaison


## INFLIBNET Centre, Gandhinagar
**Designation:** Project Officer (eSS), Project Associate (eSS)

**Duration:** <span class="exp-duration"
      data-start="2016-09-01"
      data-end="2021-05-31">
</span>

**Key Contributions:**
- Handled IP-based access, licensing, resource activation, and usage analytics
- Maintained CORAL - ERM system and university directory
- Provided training on SOUL, Koha, CORAL, DSpace
- Involved in data verification for NIRF and Shodhganga

## IIT Bhubaneswar  
**Designation:** Library Professional Trainee

**Duration:** <span class="exp-duration"
      data-start="2014-12-01"
      data-end="2016-08-31">
</span>

**Roles Included:**
- Book acquisition, Cataloguing, and Classification.
- RFID-based circulation and e-resource usage analysis
- Provided ILL/DDS Service and user support
- Managed Library Automation, Institutional Digital Repository, Library Portal, etc.

## IIT Gandhinagar
**Designation:** Library Trainee

**Duration:** <span class="exp-duration"
      data-start="2013-07-01"
      data-end="2014-07-31">
</span>

**Roles Included:**
- Book acquisition, collection development, self-rectification, book shelving, etc.
- All library professional work.

---

## Technical Skills
- **Library Systems:** Koha, SOUL, LibSys, CORAL, DSpace, SubjectPlus, VuFind, etc. 
- **Web Tools:** WordPress, Drupal, and GitHub. 
- **Operating Systems:** Windows and Linux. 
- **Office Applications:** MS Office, G-Suite, and LibreOffice. 
- **Digital Tools:** Research support and research visibility tools.
- **Data & APIs:** Usage statistics, cost per use, metadata harvesting, R programming, etc.

---

## Seminar, Webinar, Training & Workshops Attended
- Librarian Colloquium: L³ Webinar Series (Season 1), HDFC Library, Ashoka University (2026)
- Conference CLSTL 2025, IIT Gandhinagar (2025)
- Summer School on DSpace, IIT Delhi (2024)
- Author Workshops by Publishers
- Research Data Management & Open Access (SLA, ORCID, FAIR)
- Turnitin Training, CMIE Prowess, MLA Bibliography
- GeM Portal Procurement Training

---

## Memberships of Professional Bodies
### Lifetime Member
- FoSTEML – Federation of Science, Technology, Engineering & Management Libraries, India (Member since: 2026)
- SALIS – Society for the Advancement of Library and Information Science (Member since: 2025)
- CGLA – Central Government Library Association India (Member since: 2025)
- IATLIS – Indian Association of Teachers of Library and Information Science (Member since: 2024)
- ADINET – Advance Information Network of Libraries in Gujarat (Member since: 2016)
- ILA – Indian Library Association India (Member since: 2015)

---

## Contributions as Resource Person, Technical Resource Person
- LIB-TAN Monthly Talk Series – 2 (Resource Person) Webinar delivered as Library Trainee Alumni, IIT Gandhinagar.
- PDP: Design and Development of Institutional Repository Using DSpace (Resource Person) at UGC-HRDC, Sardar Patel University, Vallabh Vidyanagar.
- National workshops on DSpace, KOHA, e-Resource Management at INFLIBNET Centre, Gandhinagar
- SOUL 2.0 and ICT workshops for LIS professionals at INFLIBNET Centre, Gandhinagar


---

## References
**Mr. Rajesh Kumar**  
Deputy Librarian & Incharge, LRC, IIT Indore  
Email: rajesh@iiti.ac.in | Phone: +91-731-660-3341

**Mr. Dinesh Ranjan Pradhan**  
Scientist-D, INFLIBNET Centre, Gandhinagar  
Email: dinesh@inflibnet.ac.in

---

<script>

function calculateExperience(startDate, endDate){

    const start = new Date(startDate);

    const end = endDate === "present"
        ? new Date()
        : new Date(endDate);

    let years = end.getFullYear() - start.getFullYear();

    let months = end.getMonth() - start.getMonth();

    if(months < 0){
        years--;
        months += 12;
    }

    return {
        years: years,
        months: months,
        text: `${years} Years ${months} Months`
    };
}

function formatDate(dateString){

    if(dateString === "present"){
        return "Present";
    }

    const date = new Date(dateString);

    return date.toLocaleDateString('en-US', {
        month:'long',
        year:'numeric'
    });
}

document.querySelectorAll('.exp-duration').forEach(function(element){

    const start = element.getAttribute('data-start');

    const end = element.getAttribute('data-end');

    const experience = calculateExperience(start, end);

    element.innerHTML = `
        ${formatDate(start)} – ${formatDate(end)}
        <em>(Approx. ${experience.text})</em>
    `;
});

const overallStart = "2013-07-01";

const totalExp = calculateExperience(overallStart, "present");

document.getElementById('totalExperience').innerHTML =
`${totalExp.text} (July 2013 – Present)`;

</script>
