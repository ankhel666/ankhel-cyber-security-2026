# H1 — CyberScience

## Introduction

I started this assignment with part C, threat modeling. During our class, we had an exercise where we needed to imagine a company and think about its cyber security risks.
While thinking about a possible company, I remembered a case from my previous work experience.

A small telecom operator had its Asterisk server hacked during a long holiday period (about two weeks). The attackers used the server to make fraudulent international calls to African countries. The problem was 
discovered very late, and the company suffered significant financial losses.
I used to work as a telecommunications engineer, so this case was especially interesting to me. I decided to look for a scientific article about **VoIP Toll Fraud**.

## Part A — Science Hunt

I started searching for articles using **Google Scholar**, with search terms such as "VoIP toll fraud", "SIP fraud" and "telecom fraud review".
I wanted to find a recent review article about security problems in VoIP networks, especially attacks involving SIP servers.

I chose the following article:

**Pietri, M., Mamei, M., & Colajanni, M. (2025).**
[Telecom spam and scams in the 5G and artificial intelligence era: analyzing economic implications, technical challenges and global regulatory efforts](https://doi.org/10.1007/s10207-025-01062-8)
*International Journal of Information Security*, 24, Article 139.

The article was published on May 24, 2025, by Springer Nature.
I checked that it meets the requirements of the assignment:

- It is a scientific survey article that reviews existing research.
- It was published in a peer-reviewed academic journal.
- The journal has **JUFO level 1**.
- The article was published less than two years ago.
- The full text is available for free (Open Access).

I chose this article because it is quite recent, meets the requirements and is interesting to me personally.
In section 5.1, the authors mention **SIP trunk hacking** and explain how attackers can use vulnerable IP-PBX systems for toll fraud.
However, the article covers telecom security much more widely. It also contains technical information about telephone networks, their protocols and the reasons why some vulnerabilities still exist.
Since I worked with these technologies in the past, I was interested in reading more about them.

## Part B — Review the Review

### Key research areas

The article examines different types of telephone spam and fraud, their causes, difficulties in preventing them, and possible future solutions.

The authors consider three main areas:

- **Technical:** Telephone network technologies, vulnerabilities in protocols, different types of attacks and existing protection methods.
- **Economic:** Financial losses caused by telephone fraud and the economic interests of telecom companies and other participants.
- **Regulatory:** National legislation, international cooperation and the need for common security standards.

### What's widely agreed upon?

- Telephone fraud causes significant financial losses to individuals and businesses.
- Existing technical protection methods are useful, but none of them can completely prevent telephone fraud.
- Government regulations are important for preventing and reducing telecom fraud.
- Since telephone networks are international, countries and telecom operators need to cooperate and use more common approaches to security.

### What are the open questions?

- **Effectiveness of protection:** How effective are existing methods, such as STIR/SHAKEN, in real situations?
- **AI and fraud detection:** How can artificial intelligence help to detect suspicious calls and identify fraudulent behavior?
- **International cooperation:** How can telecom operators from different countries agree on common security standards and share information?
- **New technologies:** What new vulnerabilities may appear with the development of 6G and IoT?

In my opinion, one of the main reasons why telephone fraud still exists is that it is technically difficult to identify fraudulent calls.
Even if the Caller_ID is correct, the caller may still be a scammer.
I think AI could help by analyzing calling behavior and finding suspicious patterns. For example, a very large number of outgoing calls, unusual international destinations or many calls to 
different numbers in a short period of time.

But international regulations and cooperation between telecom operators are also very important.

## Part C — Threat Modeling Quickrun

### Company

My imaginary company is a small Telecommunications provider.
It offers different communication services, including VoIP and SIP trunks, and has approximately 200 business customers.

### Crown Jewels

The most important assets of the company are:

- **Customer data:** Personal and contact information, account details and service information.
- **Business continuity:** Availability of telephone and communication services.
- **Reputation:** Customer trust in the company and its services.
- **Money:** Company funds and financial stability.

### Bad Guys — COI (Capability, Opportunity, Intent)

Possible attackers are hackers and fraudsters who want to make money or disrupt the company's services.

- **Capability:** Attackers may have knowledge of networks and VoIP systems. They can use automated tools, known vulnerabilities or stolen passwords.
- **Opportunity:** Some services, including SIP servers, must be accessible through the internet. Weak passwords, incorrect configurations or outdated software can create opportunities for attacks.
                   Social engineering may also be used to obtain login details.
- **Intent:** The attackers may want to earn money through fraudulent international calls or make the provider's services unavailable.

### Two Risks

#### Risk 1 — DDoS Attack

Attackers send a large amount of traffic to the provider's infrastructure.
As a result, the network or VoIP services become unavailable, and customers cannot use the services normally.
This can cause financial losses, customer compensation costs and damage to the company's reputation.

**Estimated likelihood:** 50% per year.
**Estimated impact:** €30,000.

Possible losses:

- €8,000 — technical recovery and emergency support.
- €12,000 — compensation to affected customers.
- €10,000 — lost customers and contracts.

**Estimated risk:** 50% × €30,000 = **€15,000**.

#### Risk 2 — SIP Toll Fraud

Attackers get unauthorized access to a SIP server, SIP account or IP-PBX.
They use this access to make expensive international calls without the company's permission.
In some fraud schemes, calls are made to premium-rate numbers, and criminals may receive part of the money generated by these calls.
This is similar to the situation I experienced in my previous work.

The attack can cause serious financial losses, especially if nobody notices it quickly. Fraudulent calls may continue for hours or even days.

**Estimated likelihood:** 30% per year.

**Estimated impact:** €80,000.

Possible losses:

- €65,000 — fraudulent international call charges that the provider cannot recover.
- €10,000 — investigation and technical recovery.
- €5,000 — customer compensation and lost business.

**Estimated risk:** 30% × €80,000 = **€24,000**.

For this example, I assume that the provider is responsible for some international traffic charges, even if the attack started from a customer's compromised telephone system.

### Risk Comparison

| Risk | Likelihood | Impact | Estimated Risk |
|---|---:|---:|---:|
| DDoS Attack | 50% | €30,000 | €15,000 |
| SIP Toll Fraud | 30% | €80,000 | **€24,000** |

These numbers are my approximate estimates for an imaginary company, not actual statistics.

I consider a DDoS attack more likely because it can be carried out using widely available tools and does not necessarily require access to the company's accounts.
SIP Toll Fraud needs some conditions, such as vulnerable systems or compromised login details, so I estimated its probability as lower.
However, **SIP Toll Fraud has a higher estimated financial risk**. The damage can become very large if fraudulent calls are not detected quickly.

For this reason, I choose SIP Toll Fraud as the higher priority risk.

### Risk Treatment — META

For SIP Toll Fraud, I choose **Mitigate**, meaning that the company should reduce the likelihood and impact of the attack.

Possible actions:

- **International call restrictions:** Disable expensive international destinations by default and allow them only when customers need them.
- **Spending limits:** Set maximum call costs and limits for each customer.
- **Monitoring:** Automatically detect unusual calling activity and block suspicious calls.
- **Access security:** Use strong authentication, restrict access to SIP services and keep software updated.

I would not choose Eliminate, because international calling is part of the provider's business.

With these measures, the company can reduce the risk of SIP Toll Fraud and, most importantly, detect an attack before the financial losses become too large.

## References

Pietri, M., Mamei, M., & Colajanni, M. (2025). *Telecom spam and scams in the 5G and artificial intelligence era: analyzing economic implications, technical challenges and global regulatory efforts.* International Journal of Information Security, 24, Article 139. https://doi.org/10.1007/s10207-025-01062-8
