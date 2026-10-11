<!doctype html>
<html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Auditing Our Own Work</title>
<style>
:root{--bg:#faf8f4;--fg:#222;--muted:#6b6b6b;--accent:#1f5f5b;--card:#fff;--line:#e4dfd5}
@media(prefers-color-scheme:dark){:root{--bg:#16191a;--fg:#e8e6e1;--muted:#9a9a9a;--accent:#6fc2bb;--card:#1f2324;--line:#33393a}}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--fg);font:18px/1.7 Georgia,'Times New Roman',serif}
header{background:var(--accent);color:#fff;padding:64px 20px 56px}
header div{max-width:720px;margin:auto}
header small{letter-spacing:.12em;text-transform:uppercase;opacity:.8;font:600 13px system-ui,sans-serif}
header h1{margin:.4em 0 .2em;font-size:clamp(28px,5vw,42px);line-height:1.2}
header p{margin:0;opacity:.85;font:15px system-ui,sans-serif}
main{max-width:720px;margin:auto;padding:36px 20px 80px}
h2{font:700 24px system-ui,sans-serif;margin:2.2em 0 .5em;padding-bottom:.3em;border-bottom:2px solid var(--accent);color:var(--accent)}
a{color:var(--accent);word-break:break-word}
table{width:100%;border-collapse:collapse;margin:1.4em 0;font:15px/1.5 system-ui,sans-serif;background:var(--card);border:1px solid var(--line);border-radius:8px;overflow:hidden;display:block;overflow-x:auto}
th{background:var(--accent);color:#fff;text-align:left}
th,td{padding:10px 12px;border-bottom:1px solid var(--line);vertical-align:top}
li{margin:.4em 0}
#refs~p{padding-left:2em;text-indent:-2em;font-size:16px}
footer{text-align:center;color:var(--muted);font:14px system-ui,sans-serif;padding:20px}
</style></head><body>
<header><div><small>Information Assurance · Blog</small>
<h1>Auditing Our Own Work: Revisiting a Risk Assessment Through an Auditor's Eyes</h1>
<p>October 11, 2026</p></div></header>
<main><p>When our group finished its risk assessment of a small local government office, we felt good about it. We had interviewed staff, identified ten to eleven risk scenarios, scored them with an impact-times-probability matrix, recommended treatments, and shown that several "Significant" risks dropped to "Low" after treatment. It looked finished.</p>
<p>Then we reread the form pretending to be an auditor, and the confidence faded a little. An auditor does not ask, "Did you think about risk?" An auditor asks three harder questions: <strong>Do you know what you own? Do you know who is responsible for it? Can you prove your controls actually work?</strong> This post is our honest attempt to answer those questions about the office we assessed, and to explain how an asset inventory and an audit checklist would make our recommended treatments stronger. To protect the organization, I refer to it only as "the office" and describe findings in general terms, without naming people or describing how any weakness could be exploited.</p>
<h2>What the office owns, and what mattered most</h2>
<p>Our assessment grouped the office's assets into six broad categories: resident records, financial records, computers, digital records (including the database that holds them), paper records, and printed certificates. That is a reasonable starting point, but an auditor would point out that these are <em>categories</em>, not an inventory. "Computers" is not an asset register entry; "the workstation used for resident encoding, purchased in a given year, located in a given room, running a given operating system" is.</p>
<p>Looking back, three assets mattered most:</p>
<ol>
<li><strong>The resident database and its records.</strong> It holds personal information about every person the office serves. A breach here has the highest consequence: legal exposure, loss of public trust, and harm to residents. In our matrix, every scenario involving disclosure of resident data was rated Major impact.</li>
<li><strong>Financial records.</strong> These support accountability for public funds. Errors or tampering could trigger complaints, audit observations, and in the worst case legal action.</li>
<li><strong>The computers that store and process both.</strong> They are the physical doorway to the data. Theft, failure, malware, or a power problem at this layer cascades into the other two assets.</li>
</ol>
<p>Paper records and certificates matter too, because they are often the only copy of legally significant documents, but our assessment treated hazards to them as low likelihood.</p>
<h2>How these assets should be classified</h2>
<p>Our form scored <em>risks</em> but never formally classified the <em>assets</em>. An auditor would expect a simple, documented scheme. ISO/IEC 27001:2022 requires organizations to identify information and associated assets, assign owners, and classify information according to its sensitivity and legal requirements (International Organization for Standardization &amp; International Electrotechnical Commission [ISO/IEC], 2022). For a small office, a three-level scheme is enough:</p>
<table>
<thead>
<tr>
<th>Classification</th>
<th>What it covers</th>
<th>Handling expectation</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Restricted</strong></td>
<td>Resident personal data, the resident database, financial records, credentials</td>
<td>Named access only, strong authentication, encrypted or physically secured storage, tested backups</td>
</tr>
<tr>
<td><strong>Internal</strong></td>
<td>Operational files, templates, internal correspondence</td>
<td>Office staff only, routine backups</td>
</tr>
<tr>
<td><strong>Public</strong></td>
<td>Published notices, approved public forms</td>
<td>No special restrictions, but integrity still protected</td>
</tr>
</tbody>
</table>
<p>In the Philippine context, classification is not merely good practice. The Data Privacy Act of 2012 obliges organizations that process personal information to protect it with reasonable organizational, physical, and technical safeguards (Data Privacy Act of 2012, 2012). Resident records would clearly fall under "Restricted," and an auditor would expect that classification to be written down, not assumed.</p>
<h2>Who should own each asset</h2>
<p>Our treatment plan assigned responsibility to two roles working together: a records-keeping officer and IT support. For almost every risk, the owner field read the same way, with the same joint assignment and the same "within one to three months" target.</p>
<p>An auditor would flag this immediately. Joint responsibility is often no responsibility, because when two parties share a task, each can reasonably assume the other has done it. NIST's guidance on managing information security risk stresses that risk responses need clearly assigned roles and accountability (National Institute of Standards and Technology [NIST], 2012). ISO/IEC 27001 likewise expects every asset to have an <em>owner</em>, an accountable individual or role, distinct from the <em>custodian</em> who performs day-to-day handling (ISO/IEC, 2022).</p>
<p>A cleaner arrangement would be:</p>
<ul>
<li><strong>Asset owner:</strong> the official accountable for the asset's protection and for approving who may access it (for example, the records officer for resident records).</li>
<li><strong>Custodian:</strong> the person or team who operates the controls (for example, IT support who runs backups and patches).</li>
<li><strong>Approver:</strong> a senior official who signs off on accepted risks and reviews results.</li>
</ul>
<p>Related to this, the sign-off block on our form (prepared by, checked by, approved by) was never completed. To an auditor, an unsigned risk assessment is a draft, not a decision.</p>
<h2>What evidence an audit would require</h2>
<p>This is where our work was weakest, and where the lesson is most useful. Auditors work from the principle that <em>a control that cannot be evidenced does not exist</em>. Our form described existing controls in language such as "backups may also be maintained" and "access is limited to authorized staff." The word "may" is a red flag. An auditor wants to see, not hear.</p>
<p>Using the assessment approach in NIST SP 800-53A, auditors examine documents, interview personnel, and test the control in operation (NIST, 2022). Applied to our office, the evidence would look like this:</p>
<table>
<thead>
<tr>
<th>Control we recommended</th>
<th>Evidence an auditor would ask for</th>
</tr>
</thead>
<tbody>
<tr>
<td>Automated backups</td>
<td>Backup schedule and configuration; logs showing successful runs; <strong>a documented restore test</strong> with date and result</td>
</tr>
<tr>
<td>Staff training</td>
<td>Training materials, attendance records, dates, and any follow-up assessment</td>
</tr>
<tr>
<td>Access controls and password management</td>
<td>An access list showing who can reach which system; approval records for granting and removing access; a written password policy and proof it is enforced</td>
</tr>
<tr>
<td>Antivirus updates</td>
<td>Console or log evidence that definitions are current on every machine in the inventory</td>
</tr>
<tr>
<td>Physical security</td>
<td>Description of storage arrangements, key or access control records, any incident log</td>
</tr>
<tr>
<td>Backup power</td>
<td>Needs assessment, purchase or maintenance records, and a test of how long equipment stays up</td>
</tr>
<tr>
<td>Equipment maintenance</td>
<td>Maintenance schedule and service records per device</td>
</tr>
<tr>
<td>Accepted risk (natural hazards)</td>
<td>A signed risk-acceptance record naming the approver, the rationale, and a review date</td>
</tr>
</tbody>
</table>
<p>In short, every treatment needs a <strong>paper trail or system trail</strong> that a stranger could follow.</p>
<h2>The gaps an auditor would likely find</h2>
<p>Reading our own form critically, I would expect an auditor to raise the following, all in general terms:</p>
<p><strong>1. No formal asset inventory.</strong> Assets were grouped by category, with no unique identifiers, locations, owners, or classifications. Without a baseline, you cannot show that every device has antivirus, every account is reviewed, or every record set is backed up.</p>
<p><strong>2. Controls described, not demonstrated.</strong> The existing-control column relied on statements from interviews. Interviews are a legitimate form of audit evidence, but alone they are the weakest kind.</p>
<p><strong>3. Residual risk ratings that run ahead of evidence.</strong> Several risks were re-scored from Significant to Low after treatment, with remarks crediting the controls. Yet the same form shows the controls as planned or ongoing, with a one-to-three-month window to complete them. An auditor would ask: on what evidence did the probability drop? Residual risk should be re-rated only after the control is implemented <em>and verified</em>. NIST's risk assessment guidance emphasizes that risk determinations must be supported by documented reasoning and current information, and updated as conditions change (NIST, 2012).</p>
<p><strong>4. Uniform ownership and deadlines.</strong> Identical owners and identical target dates across almost every row suggest the plan was not prioritized. A Significant risk and a Moderate risk should not share the same timeline.</p>
<p><strong>5. Risk acceptance without formal approval.</strong> Accepting a risk is a management decision. The hazard risk was accepted partly because its overall score fell in the Low band, but its impact was Major. Auditors commonly challenge acceptance decisions where severity is high and the sign-off is missing.</p>
<p><strong>6. No review cycle or monitoring evidence.</strong> We proposed annual refreshes and a follow-up review, which is good, but we did not define who performs it, what it checks, or where results are recorded.</p>
<p><strong>7. Scoring consistency.</strong> The matrix is simple, which suits a small office, but its descriptions of impact are written in terms of "quality objectives" and "courts." They are inherited from a template and do not mention privacy harm to residents. An auditor would suggest tailoring them.</p>
<h2>How an asset inventory and audit checklist strengthen our treatments</h2>
<p>Reflecting on all of this, I realized our treatments were sensible but <em>unanchored</em>. Backups, training, access controls, antivirus, physical security, and backup power are exactly the right families of control. What they lacked was something to attach to and something to be measured against. An asset inventory and an audit checklist supply both.</p>
<p><strong>The asset inventory is the anchor.</strong> Once each asset has an identifier, a classification, an owner, a custodian, and a location, every treatment can be tied to specific items. "Regular automated backups" becomes "backups of these named data sets from these named machines, owned by this role." Gaps become visible: a computer that is missing from the list is a computer no one is protecting. The inventory also resolves the ownership problem, because the owner field forces a single accountable role for each row. It becomes the living register that makes our annual risk reassessment faster and more credible.</p>
<p><strong>The audit checklist is the yardstick.</strong> For each treatment, the checklist states what "implemented" means and what proof is required: <em>Is there a documented backup schedule? Was a restore tested in the last quarter? Is the access list reviewed and signed? Are antivirus definitions current on all inventoried devices? Has the accepted risk been approved in writing?</em> A checklist turns vague commitments into yes-or-no questions with dates and signatures attached. It also gives the office a way to self-audit before an external reviewer arrives, and it supplies exactly the evidence needed to justify lowering a residual risk rating honestly.</p>
<p>Together, the two tools turn a risk assessment from a one-time document into a management cycle: <strong>inventory, assess, treat, verify, review.</strong> That cycle is also the spirit behind ISO/IEC 27001's emphasis on continual improvement (ISO/IEC, 2022).</p>
<h2>Closing reflection</h2>
<p>Our group set out to help the office see its risks, and I think we did that. But the audit lens taught me that identifying risk is only half the job. The other half is being able to <em>prove</em>, to a skeptical stranger, what you have, who answers for it, and that your protections work. A small office with limited staff does not need an enterprise-grade framework to do this. It needs a one-page inventory, clear owners, a short checklist, and the habit of keeping evidence. If I could revise our form, those would be the first additions, and every treatment we recommended would be easier to defend because of them.</p>
<h2 id="refs">References</h2>
<p>Data Privacy Act of 2012, Rep. Act No. 10173 (2012). https://privacy.gov.ph/data-privacy-act/</p>
<p>International Organization for Standardization &amp; International Electrotechnical Commission. (2022). <em>Information security, cybersecurity and privacy protection: Information security management systems: Requirements</em> (ISO/IEC Standard No. 27001:2022). https://www.iso.org/standard/27001</p>
<p>National Institute of Standards and Technology. (2012). <em>Guide for conducting risk assessments</em> (NIST Special Publication 800-30, Rev. 1). U.S. Department of Commerce. https://doi.org/10.6028/NIST.SP.800-30r1</p>
<p>National Institute of Standards and Technology. (2022). <em>Assessing security and privacy controls in information systems and organizations</em> (NIST Special Publication 800-53A, Rev. 5). U.S. Department of Commerce. https://doi.org/10.6028/NIST.SP.800-53Ar5</p></main>
<footer>Risk Assessment Reflection · October 2026</footer>
</body></html>
