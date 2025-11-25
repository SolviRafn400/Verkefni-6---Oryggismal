# KEST2 Verkefni 6 – Öryggismál

> Samantekt og svör við spurningum úr nokkrum Windows öryggis- og stjórnunarlaboratoríum (BitLocker, Local Security Policy, Users & Groups, Firewall og Wireless Security). 

---

## 13.4.1.10 Packet Tracer – Configure Wireless Security

Kennari: take!  
Lykilorð: `Cisco12345`

> Ath: Settur inn samkvæmt fyrirmælum "in a file on Top".

---

## 13.2.3.7 Lab – BitLocker and BitLocker To Go

**1. Af hverju er mikilvægt að vista BitLocker endurheimtulykil (recovery key)?**  
Endurheimtulykillinn er nauðsynlegur til að komast í tölvuna ef lykilorð gleymist eða ef kerfið biður um hann (t.d. eftir vélbúnaðarbreytingar).

**2. Hvert er hlutverk TPM (Trusted Platform Module) gagnvart BitLocker?**  
TPM getur geymt dulkóðunarlykilinn og tryggir að diskurinn virki aðeins í tiltekinni tölvu (bindur notkun disksins við vélbúnað).

---

## 13.3.2.5 Lab – Configure Windows Local Security Policy

### Skref 3 – Password Policy stillingar
- Maximum password age: **90 dagar**  
- Minimum password age: **1 dagur**  
- Minimum password length: **8 stafir**  
- Password must meet complexity requirements: **Enabled**

### Skref 4 – Account Lockout Policy
**1. Hversu oft má reyna innskráningu áður en notandi er læstur?**  
5 tilraunir.  
**2. Hversu lengi á að bíða áður en reynt er aftur?**  
5 mínútur.

### Skref 6 – Aðrar Local Policies
**1. Eitthvað sem mælt er með að breyta? Af hverju?**  
Takmarka "Domains trusted to authenticate logon attempts" og tryggja að aðeins Administrators (eða viðeigandi stjórnunarteymi) hafi aðgang.

**2. Stillingar:**
Policy | Security Setting
------ | ---------------
Devices: Allow undock without having to log on | Disabled
Interactive logon: Message title for users attempting to log on | Caution
Interactive logon: Message text for users attempting to log on | Your activity is monitored. This computer is for business use only.
Interactive logon: Prompt user to change password before expiration | 7 days

---

## 13.3.3.6 Lab – Configure Users and Groups in Windows

### Part 1 – Create New Users

#### Skref 1 – Skoða Local Users and Groups
**1. Hvaða notendareikningar sjást?**  
Administrator, DefaultAccount, Guest, testUser, testUser2, tryggvi þor, user1, verkuser, WDAGUtility.

**2. Nefndu fimm hópa úr Groups:**  
Administrators, Users, Guests, Event Log Readers, Power Users.

**3. Í hvaða hópi er þinn aðalnotandi?**  
Administrators.

#### Skref 2 – Búa til nýja notendur
**4. Hvað þarf Student01 að gera við fyrstu innskráningu?**  
Skipta um lykilorð.

**5. Í hvaða hópi er User01?**  
Users.

**6. Geta meðlimir Users hópsins gert kerfisbreytingar? Hvað mega þeir?**  
Nei. Þeir geta notað forrit og fengið aðgang að flestum almennum skrám en ekki gert víðtækar kerfisbreytingar.

**7. Hverjir eru meðlimir hópsins (Users / tilgreindir hópar)?**  
Staff01, Staff02, Student01, Student02, test User, test User2, user1, verkuser.

#### Skref 3 – Staðfesta réttindi
**8. Tókst að búa til nýjan notanda sem Users hóp? Útskýrðu.**  
Nei, Users hópur hefur ekki heimildir til að búa til nýja notendur.

**9. Gatstu farið á www.cisco.com?**  
Já, Users hópur má nota internetið.

### Part 2 – Create New Groups
**10. Með ITEStaff merkt, hvað mega meðlimir gera í möppunni?**  
Read & Execute, List Folder Contents, Read.

**11. Hvaða auka heimild myndir þú velja?**  
Full Control.

### Part 3 – Modify User and Group Permissions
**12. Gatstu búið til möppu C:\Students\Student02 og textaskrá?**  
Já. Notendur í ITEStudent hafa fullan aðgang þar.

**13. Gatstu búið til möppu C:\Staff\Student02 og textaskrá?**  
Að hluta. Student01 (ITEStudent) hefur ekki aðgang að Staff möppunni, en hefur fullan aðgang í Students.

**14. Gatstu nálgast innihald í Student01 og Student02 möppum?**  
Aðeins Student02 sem á sína möppu; enginn aðgangur í Student01 möppuna.

**15. Gatstu nálgast Staff, Student\Student01 og Student\Student02 sem Staff01?**  
Já. ITEStaff meðlimir hafa aðgang að C:\Staff og C:\Student (ekki neitað write).

#### Skref 2 – Disable a user account
**16. Gatstu skráð þig inn sem Staff02?**  
Nei, reikningurinn er óvirkur (disabled).

### Reflection
**17. Hvernig gefurðu öllum ITEStaff stjórnandaheimildir á vélinni?**  
Bæta hópnum ITEStaff við built-in Administrators hópinn: Computer Management > Local Users and Groups > Groups > Administrators > Add > ITEStaff.

**18. Hvernig neitarðu öllum nema eiganda aðgang að skrá?**  
Eiganda gefinn Full Control; öðrum hópum og notendum er Explicit Deny á allar heimildir.

---

## 13.3.4.6 Lab – Configure Windows Firewall

**1. Sést shared mappan Cisco undir PC-1?**  
True.

**2. Kostir Windows Firewall?**  
Hindrar óviðkomandi aðgang (hackers / malware) frá neti eða interneti og stýrir heimilum samskiptum.

**3. Neikvæð afleiðing of margra undantekninga?**  
Of margar exceptions auka árásarflöt og áhættu.

**4. Geturðu tengst PC-1 og séð Cisco möppuna?**  
Nei.

**5. Villuskilaboð á PC-2?**  
"Windows cannot access PC-1."

**6. Geturðu tengst Computer 1? Útskýrðu.**  
Já, File and Printer Sharing er ekki lokað af firewall.

**7. Stutt heiti fjögurra þjónusta í Customize Service Settings glugga:**  
AxinstSv, AjRouter, Appinfo, ALG.

**8. Fjögur Specific ICMP tegundir:**  
Packet Too Big, Source Quench, Echo Request, Time Exceeded.

### Reflection
**Hvers vegna gæti þurft að breyta firewall stillingum?**  
Til að leyfa löglegum forritum/þjónustum að virka (leikjaþjónusta, fjarfundaforrit, sérsniðin þjónusta), eða til að herða öryggi með því að loka óþarfa portum.

---

## Athugasemdir
- Texti snyrtilega formaður.
- Spurningar og svör haldin í samræmi við upphafleg gögn.
- Lykilorð og viðkvæmar prófunarupplýsingar ekki nota í raunkera.
