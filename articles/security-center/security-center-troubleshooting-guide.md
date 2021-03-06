---
title: Handleiding voor het oplossen van problemen met Azure Security Center | Microsoft Docs
description: Dit document helpt bij het oplossen van problemen in Azure Security Center.
services: security-center
documentationcenter: na
author: YuriDio
manager: swadhwa
editor: 
ms.assetid: 44462de6-2cc5-4672-b1d3-dbb4749a28cd
ms.service: security-center
ms.devlang: na
ms.topic: hero-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: yurid
translationtype: Human Translation
ms.sourcegitcommit: b9f4a8b185f9fb06f8991b6da35a5d8c94689367
ms.openlocfilehash: dbbec729c14d0d9dc5781e7a88a1db3f66f7df97


---
# <a name="azure-security-center-troubleshooting-guide"></a>Handleiding voor het oplossen van problemen met Azure Security Center
Deze handleiding is bedoeld voor IT-specialisten, informatiebeveiligingsanalisten en cloudbeheerders van organisaties die Azure Security Center gebruiken en biedt procedures voor het oplossen van problemen met Azure Security Center.

## <a name="troubleshooting-guide"></a>Handleiding voor het oplossen van problemen
In deze handleiding wordt uitgelegd hoe u problemen oplost die betrekking hebben op Security Center. In de meeste gevallen vindt probleemoplossing in Security Center plaats door eerst de records in het [Controlelogboek](https://azure.microsoft.com/updates/audit-logs-in-azure-preview-portal/) van het onderdeel met de fout te raadplegen. Met controlelogboeken kunt u het volgende bepalen:

* Welke bewerkingen er hebben plaatsgevonden
* Wie de bewerking heeft gestart
* Wanneer de bewerking is uitgevoerd
* De status van de bewerking
* De waarden van andere eigenschappen die u kunnen helpen bij het onderzoeken van het probleem

In het controlelogboek staan alle schrijfbewerkingen (PUT, POST, DELETE) die op uw resources zijn uitgevoerd, maar er staan geen leesbewerkingen (GET) in.

## <a name="troubleshooting-monitoring-agent-installation-in-windows"></a>Problemen oplossen met de installatie van de controleagent in Windows
De controleagent van Security Center wordt gebruikt om gegevens te verzamelen. Nadat het verzamelen van gegevens is ingeschakeld en de agent juist is geïnstalleerd op de doelcomputer, worden als het goed is deze processen uitgevoerd:

* ASMAgentLauncher.exe - Azure Monitoring Agent 
* ASMMonitoringAgent.exe - Azure Security Monitoring-uitbreiding
* ASMSoftwareScanner.exe – Azure Scan Manager

De extensie Azure Security Monitoring scant op diverse voor de beveiliging relevante configuraties en verzamelt beveiligingslogboeken vanaf de virtuele machine. De scanbeheerder wordt gebruikt als patch-scanner.

Als de installatie succesvol is uitgevoerd, ziet u een vermelding die vergelijkbaar is met die in de controlelogboeken voor het doel-VM:

![Controlelogboeken](./media/security-center-troubleshooting-guide/security-center-troubleshooting-guide-fig1.png)

U kunt ook meer informatie over het installatieproces krijgen door de logboekbestanden van de agenten te lezen, die zich bevinden op *%systemdrive%\windowsazure\logs* (bijvoorbeeld: C:\WindowsAzure\Logs).

> [!NOTE]
> Als de Azure Security Center-agent zich niet goed gedraagt, dient u het doel-VM opnieuw op te starten omdat er geen opdracht is om de agent te stoppen en te starten.


Als u nog steeds problemen ondervindt met het verzamelen van gegevens, voert u de volgende stappen uit om de agent te verwijderen:

1. Selecteer in **Azure Portal** de virtuele machine waarop zich problemen met het verzamelen van gegevens voordoen en klik op **Extensies**.
2. Klik met de rechtermuisknop op **Microsoft.Azure.Security.Monitoring** en selecteer **Verwijderen**.

![De agent verwijderen](./media/security-center-troubleshooting-guide/security-center-troubleshooting-guide-fig4.png)

De extensie Azure Security Monitoring wordt nu binnen enkele minuten automatisch opnieuw geïnstalleerd.

## <a name="troubleshooting-monitoring-agent-installation-in-linux"></a>Problemen oplossen met de installatie van de controleagent in Linux
Bij het oplossen van problemen met de installatie van VM-agent op een Linux-systeem, moet u controleren of de uitbreiding is gedownload naar/var/lib/waagent/. U kunt de onderstaande opdracht uitvoeren om te controleren of deze is geïnstalleerd:

`cat /var/log/waagent.log` 

De andere logboekbestanden die u kunt bekijken voor het oplossen van problemen zijn: 

* /var/log/mdsd.err
* /var/log/azure/

In een werkend systeem ziet u een verbinding met het mdsd-proces op TCP 29130. Dit is de communicatie tussen syslog en het mdsd-proces. U kunt dit gedrag controleren door de onderstaande opdracht uit te voeren:

`netstat -plantu | grep 29130`

## <a name="troubleshooting-endpoint-protection-not-working-properly"></a>Oplossen van problemen met niet goed werkende eindpuntbeveiliging

De gastagent is het bovenliggende proces van alles wat de [Microsoft Antimalware](../security/azure-security-antimalware.md)-extensie doet. Wanneer het proces van de gastagent mislukt, kan de Microsoft Antimalware die wordt uitgevoerd als onderliggend proces van de gastagent ook mislukken.  In dergelijke scenario's wordt aanbevolen de volgende opties te controleren:

- Als de doel-VM een aangepaste installatiekopie is en de maker van de VM nooit een gastagent heeft geïnstalleerd.
- Als het doel een Linux-VM in plaats van een Windows-VM is, mislukt het installeren van de Windows-versie van de anti-malware-extensie op een Linux-VM. De Linux-gastagent heeft specifieke vereisten voor het besturingssysteem en de vereiste pakketten. Als niet aan deze vereisten wordt voldaan, werkt de VM-agent ook niet. 
- Als de VM is gemaakt met een oudere versie van gastagent. Als dat het geval is, houd er dan rekening mee dat een aantal oude agents niet automatisch kunnen bijwerken naar de nieuwe versie en dat dit tot dit probleem kan leiden. Gebruik altijd de nieuwste versie van gastagent als u uw eigen installatiekopieën maakt.
- Sommige beheersoftware van derden kan de gastagent uitschakelen of toegang tot bepaalde bestandslocaties blokkeren. Als u beheersoftware van derden op de VM hebt geïnstalleerd, zorgt u ervoor dat de agent op de uitsluitingslijst staat.
- Bepaalde firewallinstellingen of netwerkbeveiligingsgroepen (NSG) blokkeren mogelijk het netwerkverkeer naar en van de gastagent.
- Een toegangsbeheerlijst (ACL) blokkeert mogelijk de toegang tot de schijf.
- Onvoldoende schijfruimte kan er voor zorgen dat de gastagent niet goed functioneert. 

De gebruikersinterface van Microsoft Antimalware is standaard uitgeschakeld. Zie [Enabling Microsoft Antimalware User Interface on Azure Resource Manager VMs Post Deployment](https://blogs.msdn.microsoft.com/azuresecurity/2016/03/09/enabling-microsoft-antimalware-user-interface-post-deployment/) (De Microsoft Antimalware-gebruikersinterface inschakelen op Azure Resource Manager-VM's na implementatie) voor meer informatie over hoe u deze kunt inschakelen.

## <a name="troubleshooting-problems-loading-the-dashboard"></a>Problemen oplossen met het laden van het dashboard

Als u problemen ondervindt met het laden van het dashboard van Security Center, moet u ervoor zorgen dat de gebruiker die het Security Center-abonnement registreert (de eerste gebruiker die Security Center voor het abonnement opent) en de gebruiker die het verzamelen van gegevens inschakelt, in het abonnement de rol van *Eigenaar* of *Inzender* hebben. Vanaf dat moment kunnen ook gebruikers die in het abonnement de rol van *Lezer* hebben, het dashboard weergeven, en waarschuwingen, aanbevelingen en het beleid bekijken.

## <a name="contacting-microsoft-support"></a>Contact opnemen met Microsoft-ondersteuning
Bepaalde problemen kunnen worden geïdentificeerd aan de hand van de richtlijnen in dit artikel. Andere problemen vindt u ook beschreven in het openbare [Forum](https://social.msdn.microsoft.com/Forums/en-US/home?forum=AzureSecurityCenter) van Security Center. Als u aanvullende hulp nodig hebt om bepaalde problemen op te lossen, kunt u via **Azure Portal** een nieuwe ondersteuningsaanvraag openen. Dit doet u als volgt: 

![Microsoft-ondersteuning](./media/security-center-troubleshooting-guide/security-center-troubleshooting-guide-fig2.png)

## <a name="see-also"></a>Zie ook
In dit document hebt u kunnen lezen hoe u het beveiligingsbeleid configureert in Azure Security Center. Zie de volgende onderwerpen voor meer informatie over Azure Security Center:

* [Azure Security Center Planning and Operations Guide](security-center-planning-and-operations-guide.md) (Gids voor de planning en werking van Azure Security Center): leer de ontwerpoverwegingen kennen en leer hiervoor te plannen voor de overstap naar Azure Security Center.
* [Security health monitoring in Azure Security Center](security-center-monitoring.md) (Beveiligingsstatus controleren in Azure Security Center): meer informatie over het controleren van de status van uw Azure-resources
* [Beveiligingswaarschuwingen beheren en erop reageren in Azure Security Center](security-center-managing-and-responding-alerts.md): leer hoe u beveiligingswaarschuwingen kunt beheren en erop kunt reageren
* [Partneroplossingen controleren met Azure Security Center](security-center-partner-solutions.md): leer hoe u de integriteitsstatus van uw partneroplossingen kunt controleren.
* [Veelgestelde vragen over Azure Security Center](security-center-faq.md): raadpleeg veelgestelde vragen over het gebruik van de service
* [Azure-beveiligingsblog](http://blogs.msdn.com/b/azuresecurity/): lees blogberichten over de beveiliging en naleving van Azure




<!--HONumber=Feb17_HO3-->


