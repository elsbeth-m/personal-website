---
title: 'AMUSec 2024 event'
description: 'Some of my personal notes and opinion on the conferences that I saw during the AMUsec 2024 event'
pubDate: '22 March 2024'
heroImage: '/AMUSEC2024.jpg'
---

DRAFT NOTES!

### Secure Element
Conference sur  The future of the embedded Secure Element – The next generation of Secure Enclaves for IoT and Digital Applications

Resume : 
An embedded Secure Element (eSE) is a standalone tamper-resistant hardware component embedded within electronic devices, such as smartphones, wearables, hardware wallets, or other similar devices, to securely store sensitive information, data, and applications. It is also certified to the highest security standard in the industry (Common Criteria). The new generation of Secure Enclaves can also play the role of a Secure Element and represent the cornerstone of embedded security for the next generation of SoC, ASIC, and application processors. A Secure Enclave provides unique benefits and capabilities for key use cases, empowering developers to fortify their systems, building a robust root of trust, enhancing data privacy, and fostering trust among end-users. Chipset designers can integrate the Secure Enclave into their SoC design, enabling device makers to reduce their BOM and achieve the most efficient combination of power, size, and performance, while maintaining the same level of security. Moreover, the secure enclave can also be certified as a standalone secure element in following the same security standards.


Secure Elements : resistant au tamper modification, env d'exec isolee par exemple le cpu pour se premunir des attaques, proteger des secrets. 
Haut niveau de securite, pour paiement, des tickets, finances etc. 

Security needs to be tightly embedded at the heat of any system. 
Physical world : SE (secure element)
Connected world :  Connected device  = MCU + eSE <-> cloud HSM
Future connected world : eSE inside the MCU

Advantages of integrated secure element : better integration (low power consumption, function-device interaction) ....

### IoT security standards and regulations  
STM microelectronics nouveautes du 2024 targeting SESIP3 : STM32U0 140 CoreMark, 48MHz Cortex-M0+, STM32WBA5/6 407 CoreMark, 100MHz Cortex-M33, STM32MP2 Dual 1.5 GHz Cortex-A35 400 MHz Cortex-M33. 


### Simple regard pratique sur l'obligation de sensibilisation dans le cyber score
CyberScore : Strategie de souveranite numerique, avoir sur le sol national les competences necessaires pour assurer la securite
em viguer mais il y a rien encore? 
CyberScore:  prestataire d'audit de systemes d'information (PASI). 
Sensibilisation : information
Formation : transmettre une competence

### Course on pentest 

A very interesting course with professor Alexis Bonnecaze from Polytech Marseille
The importance of pentest, what do you need to become a pentester (gotta be curious but honest!) and have technical skills. 
Different approaches : black box, white box, grey box. 
Different teams : red team for the attack, blue team for the defense, purple team for the coordination of both teams. Some other stakeholders such as management, development, legal. 

the basic standards and methodologies :  mitre att&ck, owasp, nist, ptes etc. q

Some rules for pentesters : the scope is well defined and planified, as well as the way of collecting info, the attack type and exploit, do a report and communicate the results. 

How to define the scope :  gotta have the authorisation from the ressource owner, the contract protects the different actors, and there are some non-disclosure agreements among other legal agreements. 

About the information collection : 
it can be passive through OSINT for example, or active by using scan tools for instance. 

tool : the harverster 

for the active collection : nmap hehe 

### The future of elliptic curves
difficultés initales : calculer la cardinalité d'une courbe? On ne savait pas faire donc on faisait des courbes supersinguliers mais faciles a attaquer par transfert (MOV et frey rück) 
apparement pas tres fiable au tout debut, on en faisait pas tres confiance. 
Shor n'a encore jamais été implémenté -> harvest now, decrypt later du point de vue de l'attaquant! Ca pause des risques au niveau du choffrement mais pas de la signature ni de l'authentifcation. 

### network segmentation contraintes


### NIS2, une loi de sélection naturelle ?
Parce que ca demande enormement de préparation, donc il faudra faire appel a des experts qui pourront apporter une démarche de construction de la sécurité
