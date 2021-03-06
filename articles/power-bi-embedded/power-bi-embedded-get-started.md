---
title: Aan de slag met Microsoft Power BI Embedded
description: Power BI Embedded, voeg interactieve Power BI-rapporten toe aan uw BI-toepassing (Business Intelligence)
services: power-bi-embedded
documentationcenter: 
author: guyinacube
manager: erikre
editor: 
tags: 
ms.assetid: 4787cf44-5d1c-4bc3-b3fd-bf396e5c1176
ms.service: power-bi-embedded
ms.devlang: NA
ms.topic: hero-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/11/2017
ms.author: asaxton
translationtype: Human Translation
ms.sourcegitcommit: c1cd1450d5921cf51f720017b746ff9498e85537
ms.openlocfilehash: 4afa8d2c7f8ec1942521ba5fa131967dfd581c91
ms.lasthandoff: 03/14/2017

---
# <a name="get-started-with-microsoft-power-bi-embedded"></a>Aan de slag met Microsoft Power BI Embedded

**Power BI Embedded** is een Azure-service waarmee ontwikkelaars van toepassingen interactieve Power BI-rapporten aan hun eigen toepassingen kunnen toevoegen. **Power BI Embedded** werkt met bestaande toepassingen zonder dat deze opnieuw hoeven te worden ontworpen en zonder de manier te hoeven wijzigen waarop gebruikers zich aanmelden.

Resources voor **Microsoft Power BI Embedded** worden ingericht via [Azure ARM-API's](https://msdn.microsoft.com/library/mt712306.aspx). In dit geval is de resource die u inricht een **Power BI-werkruimteverzameling**.

![](media/power-bi-embedded-get-started/introduction.png)

## <a name="create-a-workspace-collection"></a>Een werkruimteverzameling maken

Een **werkruimteverzameling** is een Azure-resource op het hoogste niveau en een container voor de inhoud die wordt ingesloten in uw toepassing. U kunt op twee manieren een **werkruimteverzameling** maken:

* Handmatig met de Azure-portal
* Programmatisch met behulp van de Azure Resource Manager (ARM) API's

Hier volgen de stappen voor het bouwen van een **werkruimteverzameling** met behulp van de Azure-portal.

1. Open de **Azure-portal**: [http://portal.azure.com](http://portal.azure.com) en meld u aan.
2. Klik op **+ Nieuw** boven in het venster.
   
   ![](media/power-bi-embedded-get-started/create-workspace-1.png)
3. Klik onder **Gegevens en analyse** op **Power BI Embedded**.
4. Voer op de **blade Werkruimteverzameling** de vereiste gegevens in. Informatie over **prijzen** vindt in [Prijzen van Power BI Embedded](http://go.microsoft.com/fwlink/?LinkID=760527).
   
   ![](media/power-bi-embedded-get-started/create-workspace-2.png)
5. Klik op **Maken**.

Het duurt even voordat de **werkruimteverzameling** is ingericht. Wanneer dit is voltooid, wordt u naar de blade **Workspace Collection Blade** (Werkruimteverzameling) gebracht.

   ![](media/power-bi-embedded-get-started/create-workspace-3.png)

De **Creation Blade** (Blade Maken) bevat de informatie die u nodig hebt om de API's aan te roepen die werkruimten maken en om hierin inhoud te implementeren.

<a name="view-access-keys"/>

## <a name="view-power-bi-api-access-keys"></a>Toegangssleutels voor Power BI API

Een van de belangrijkste stukjes informatie die nodig zijn om Power BI REST API's aan te roepen, zijn de **toegangssleutels**. Deze worden gebruikt voor het genereren van de **app-tokens** die worden gebruikt om uw API-aanvragen te verifiëren. U geeft uw **toegangssleutels** weer door te klikken op **Toegangssleutels** op de **blade Instellingen**. Voor meer informatie over **app-tokens** verwijzen wij u naar [Authenticating and authorizing with Power BI Embedded](power-bi-embedded-app-token-flow.md) (Verifiëren en autoriseren met Power BI Embedded).

   ![](media/power-bi-embedded-get-started/access-keys.png)

U ziet dat u twee sleutels hebt.

   ![](media/power-bi-embedded-get-started/access-keys-2.png)

Kopieer deze sleutels en sla ze veilig op in uw toepassing. Het is belangrijk dat u deze sleutels net zo behandelt als wachtwoorden, omdat deze toegang bieden tot de inhoud in uw **werkruimteverzameling**.

Hoewel er twee sleutels worden vermeld, hebt u er slechts één tegelijk nodig. De tweede sleutel biedt u de mogelijk periodiek opnieuw sleutels te genereren, zonder dat toegang tot de service wordt onderbroken.

Nu u een exemplaar van Power BI voor uw toepassing en **toegangssleutels** hebt, kunt u een rapport in uw eigen app importeren. Voordat u een rapport leert importeren, kunt u in de volgende sectie lezen hoe u Power BI-gegevenssets en -rapporten maakt om deze in een app in te sluiten.

## <a name="working-with-workspaces"></a>Werken met werkruimten

Nadat u de verzameling met werkruimten hebt gemaakt, moet u een werkruimte maken voor rapporten en gegevenssets. U moet de [Post Workspace REST-API](https://msdn.microsoft.com/library/azure/mt711503.aspx) gebruiken om een werkruimte te maken.

## <a name="create-power-bi-datasets-and-reports-to-embed-into-an-app-using-power-bi-desktop"></a>Power BI-gegevenssets en -rapporten maken om in een app in te sluiten met behulp van Power BI Desktop

Nu u een exemplaar van Power BI voor uw toepassing hebt gemaakt en **toegangssleutels** hebt, moet u de Power BI-gegevenssets en -rapporten maken die u wilt insluiten. Gegevenssets en rapporten kunnen worden gemaakt met behulp van **Power BI Desktop**. U kunt [Power BI Desktop gratis](https://go.microsoft.com/fwlink/?LinkId=521662) downloaden. Of u downloadt de [Retail Analysis Sample PBIX](http://go.microsoft.com/fwlink/?LinkID=780547) als u snel aan de slag wilt.

> [!NOTE]
> Meer informatie over het gebruik van **Power BI Desktop** vindt u in [Aan de slag met Power BI Desktop](https://powerbi.microsoft.com/guided-learning/powerbi-learning-0-2-get-started-power-bi-desktop).

Met **Power BI Desktop** maakt u verbinding met uw gegevensbron door een kopie van de gegevens te importeren in **Power BI Desktop** of door een rechtstreekse verbinding te maken met de gegevensbron via **DirectQuery**.

Dit zijn de verschillen tussen **Importeren** en **DirectQuery**.

| Importeren | DirectQuery |
| --- | --- |
| Tabellen, kolommen *en gegevens* worden geïmporteerd of gekopieerd naar **Power BI Desktop**. Als u met visualisaties werkt, vraagt **Power BI Desktop** een kopie van de gegevens op. Als u wilt zien welke wijzigingen zijn doorgevoerd in de onderliggende gegevens, moet u deze vernieuwen of een volledige, actuele gegevensset opnieuw importeren. |Alleen *tabellen en kolommen* worden geïmporteerd of gekopieerd naar **Power BI Desktop**. Wanneer u met visualisaties werkt, voert **Power BI Desktop** query’s uit op de onderliggende gegevensbron. Dit betekent dat u altijd actuele gegevens bekijkt. |

Meer informatie over het maken van een verbinding met een gegevensbron vindt u in [Verbinding maken met een gegevensbron](power-bi-embedded-connect-datasource.md).

Nadat u uw werk in **Power BI Desktop** hebt opgeslagen, wordt een PBIX-bestand gemaakt. Dit bestand bevat het rapport. Daarnaast bevat de PBIX ofwel de volledige gegevensset, als u gegevens importeert, ofwel, als u **DirectQuery** gebruikt, alleen een gegevensset-schema. U kunt met de [Power BI Import API](https://msdn.microsoft.com/library/mt711504.aspx) de PBIX programmatisch implementeren in uw werkruimte.

> [!NOTE]
> **Power BI Embedded** heeft aanvullende API's voor het wijzigen van de server en database waarnaar uw gegevensset wijst en het instellen van accountreferenties die door de gegevensset wordt gebruikt voor het maken van een verbinding met uw database. Zie [Post SetAllConnections](https://msdn.microsoft.com/library/mt711505.aspx) en [Patch Gateway Datasource](https://msdn.microsoft.com/library/mt711498.aspx).

## <a name="create-power-bi-datasets-and-reports-using-apis"></a>Power BI-gegevenssets en -rapporten maken met behulp van API's

### <a name="datsets"></a>Gegevenssets

U kunt gegevenssets in Power BI Embedded maken met behulp van de REST-API. Vervolgens kunt u gegevens naar uw gegevensset pushen. Hierdoor kunt u met gegevens werken zonder Power BI Desktop te gebruiken. Zie [Post Datasets](https://msdn.microsoft.com/library/azure/mt778875.aspx) (Gegevenssets posten) voor meer informatie.

### <a name="reports"></a>Rapporten

U kunt een rapport uit een gegevensset rechtstreeks in uw toepassing maken met de JavaScript-API. Zie [Create a new report from a dataset in Power BI Embedded](power-bi-embedded-create-report-from-dataset.md) (Een nieuw rapport maken uit een gegevensset in Power BI Embedded) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Aan de slag met het voorbeeld](power-bi-embedded-get-started-sample.md)  
[Verifiëren en autoriseren in Power BI Embedded](power-bi-embedded-app-token-flow.md)  
[Een rapport insluiten](power-bi-embedded-embed-report.md)  
[Een nieuw rapport maken uit een gegevensset in Power BI Embedded](power-bi-embedded-create-report-from-dataset.md)
[Rapporten opslaan](power-bi-embedded-save-reports.md)  
[Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-get-the-desktop/)  
[Voorbeeld van ingesloten JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
Nog vragen? [Probeer de Power BI-community](http://community.powerbi.com/)


