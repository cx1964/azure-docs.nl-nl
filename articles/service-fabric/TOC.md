
# Overzicht
## [Wat is Service Fabric?](service-fabric-overview.md)
## [Uitleg over microservices](service-fabric-overview-microservices.md)
## [Toepassingsscenario's](service-fabric-application-scenarios.md)
## [Patronen en scenario's](service-fabric-patterns-and-scenarios.md)
## [Architectuur](service-fabric-architecture.md)
## [Terminologie](service-fabric-technical-overview.md)
## [Inleiding](service-fabric-content-roadmap.md)

# Aan de slag
## De ontwikkelomgeving instellen
### [Windows](service-fabric-get-started.md)
### [Linux](service-fabric-get-started-linux.md)
### [Mac OS](service-fabric-get-started-mac.md)
## Uw eerste toepassing maken
### [C# op Windows](service-fabric-create-your-first-application-in-visual-studio.md)
### [Java op Linux](service-fabric-create-your-first-linux-application-with-java.md)
### [C# op Linux](service-fabric-create-your-first-linux-application-with-csharp.md)
## [Implementeren van apps op een lokale cluster](service-fabric-get-started-with-a-local-cluster.md)
## [.NET-apps in een container implementeren](service-fabric-host-app-in-a-container.md)
## [Uw eerste cluster maken in Azure](service-fabric-get-started-azure-cluster.md)
## [Uw eerste zelfstandige -cluster maken](service-fabric-get-started-standalone-cluster.md)
## [Uw eerste app in een container maken](service-fabric-get-started-containers.md)

# Procedures
## Een toepassing bouwen
  
### Concepten
#### [Ondersteunde programmeermodellen](service-fabric-choose-framework.md)
#### [Toepassingsmodel](service-fabric-application-model.md)
#### [Hostingmodel](service-fabric-hosting-model.md)
#### [Servicemanifest-resources](service-fabric-service-manifest-resources.md)
#### [Servicestatus](service-fabric-concepts-state.md)
#### [Service partitioneren](service-fabric-concepts-partitioning.md)
#### [Beschikbaarheid van services](service-fabric-availability-services.md)
#### [Schaalbaarheid van toepassingen](service-fabric-concepts-scalability.md)
#### [ASP.NET Core](service-fabric-reliable-services-communication-aspnetcore.md)

### [App-capaciteit plannen](service-fabric-capacity-planning.md)

### Een service bouwen die door een gast kan worden uitgevoerd
#### [Een toepassing implementeren die door een gast kan worden uitgevoerd](service-fabric-deploy-existing-app.md)
#### [Meerdere toepassingen implementeren die door gasten kunnen worden uitgevoerd](service-fabric-deploy-multiple-apps.md)

### Een containerservice bouwen
#### [Overzicht](service-fabric-containers-overview.md)
#### [Windows-container implementeren](service-fabric-deploy-container.md)
#### [Linux-container implementeren](service-fabric-deploy-container-linux.md)
#### [Docker Compose (preview)](service-fabric-docker-compose.md)
#### [Resourcebeheer voor containers en services](service-fabric-resource-governance.md)
#### [Volume en stuurprogramma's voor logboekregistratie](service-fabric-containers-volume-logging-drivers.md)

### Een Reliable Service-service bouwen
#### [Overzicht](service-fabric-reliable-services-introduction.md)
#### Concepten
##### [Levenscyclus van Reliable Services - C#](service-fabric-reliable-services-lifecycle.md)
##### [Levenscyclus van Reliable Services - Java](service-fabric-reliable-services-lifecycle-java.md)

#### Betrouwbare verzamelingen
##### [Betrouwbare verzamelingen](service-fabric-reliable-services-reliable-collections.md)
##### [Richtlijnen en aanbevelingen voor betrouwbare verzamelingen](service-fabric-reliable-services-reliable-collections-guidelines.md)
##### [Werken met betrouwbare verzamelingen](service-fabric-work-with-reliable-collections.md)
##### [Transacties en vergrendelingen](service-fabric-reliable-services-reliable-collections-transactions-locks.md)
##### [Betrouwbare gelijktijdige wachtrij](service-fabric-reliable-services-reliable-concurrent-queue.md)
##### [Betrouwbare verzamelingserialisatie](service-fabric-reliable-services-reliable-collections-serialization.md)
##### [Beheer van betrouwbare status en interne werking van betrouwbare verzameling](service-fabric-reliable-services-reliable-collections-internals.md)

#### Aan de slag
##### [C# op Windows](service-fabric-reliable-services-quick-start.md)
##### [Java op Linux](service-fabric-reliable-services-quick-start-java.md)

#### [Configureren](service-fabric-reliable-services-configuration.md)
#### [Meldingen verzenden](service-fabric-reliable-services-notifications.md)
#### [Back-up en herstel](service-fabric-reliable-services-backup-restore.md)

#### Communiceren met services
##### [Communiceren via Betrouwbare services](service-fabric-reliable-services-communication.md)
##### [Service voor externe toegang - C#](service-fabric-reliable-services-communication-remoting.md)
##### [Service voor externe toegang - Java](service-fabric-reliable-services-communication-remoting-java.md)
##### [WCF](service-fabric-reliable-services-communication-wcf.md)
##### [Beveiligde communicatie - C#](service-fabric-reliable-services-secure-communication.md)
##### [Beveiligde communicatie - Java](service-fabric-reliable-services-secure-communication-java.md)

#### [Geavanceerd gebruik](service-fabric-reliable-services-advanced-usage.md)

### Een Reliable Actor-service bouwen
#### [Overzicht](service-fabric-reliable-actors-introduction.md)
#### Concepten
##### [Architectuur](service-fabric-reliable-actors-platform.md)
##### [Levenscyclus en garbagecollection](service-fabric-reliable-actors-lifecycle.md)
##### [Statusbeheer](service-fabric-reliable-actors-state-management.md)
##### [Polymorfisme](service-fabric-reliable-actors-polymorphism.md)
##### [Herintreding](service-fabric-reliable-actors-reentrancy.md)
##### [Typeserialisatie](service-fabric-reliable-actors-notes-on-actor-type-serialization.md)

#### Aan de slag
##### [C# op Windows](service-fabric-reliable-actors-get-started.md)
##### [Java op Linux](service-fabric-reliable-actors-get-started-java.md)

#### [Meldingen verzenden](service-fabric-reliable-actors-events.md) 
#### [Timers en herinneringen instellen](service-fabric-reliable-actors-timers-reminders.md)
#### [KvsActorStateProvider configureren](service-fabric-reliable-actors-kvsactorstateprovider-configuration.md)
#### [Communicatie-instellingen configureren](service-fabric-reliable-actors-fabrictransportsettings.md) 
#### [ReliableDictionaryActorStateProvider configureren](service-fabric-reliable-actors-reliabledictionarystateprovider-configuration.md)

### Communiceren met services
#### [Servicecommunicatie](service-fabric-connect-and-communicate-with-services.md)
#### [DNS-service](service-fabric-dnsservice.md)
#### [Omgekeerde proxy](service-fabric-reverseproxy.md)
#### [Omgekeerde proxy voor veilige communicatie configureren](service-fabric-reverseproxy-configure-secure-communication.md)

### [Een webfront-end toevoegen](service-fabric-add-a-web-frontend.md)

### In een IDE werken
#### [Aan de slag met Eclipse-invoegtoepassing voor Java-ontwikkeling](service-fabric-get-started-eclipse.md)
#### [Apps beheren in Visual Studio](service-fabric-manage-application-in-visual-studio.md)
#### [Beveiligde verbindingen configureren in Visual Studio](service-fabric-visualstudio-configure-secure-connections.md)
#### [Uw toepassing configureren voor meerdere omgevingen](service-fabric-manage-multiple-environment-app-configuration.md)

### Beveiliging configureren
#### [Toepassingsgeheimen beheren](service-fabric-application-secret-management.md)  
#### [Beveiligingsbeleid configureren voor uw toepassing](service-fabric-application-runas-security.md)

### Fouten opsporen
#### [Fouten opsporen in een C#-service in Visual Studio](service-fabric-debugging-your-application.md)
#### [Fouten opsporen in een Java-service in Eclipse](service-fabric-debugging-your-application-java.md)
#### [Veelvoorkomende fouten en uitzonderingen](service-fabric-errors-and-exceptions.md)

### Lokaal bewaken en diagnoses uitvoeren
#### [Windows](service-fabric-diagnostics-how-to-monitor-and-diagnose-services-locally.md)
#### [Linux](service-fabric-diagnostics-how-to-monitor-and-diagnose-services-locally-linux.md)

### Migreren uit Cloud Services
#### [Cloud Services vergelijken met Service Fabric](service-fabric-cloud-services-migration-differences.md)
#### [Migreren naar Service Fabric](service-fabric-cloud-services-migration-worker-role-stateless-service.md)
#### [Aanbevolen procedures](/azure/architecture/service-fabric/migrate-from-cloud-services)

## Toepassingslevenscyclus beheren
### [Overzicht](service-fabric-application-lifecycle.md)
### [Toepassingspakket maken](service-fabric-package-apps.md)
### [Meer informatie over de instelling ImageStoreConnectionString](service-fabric-image-store-connection-string.md)
### Toepassingen implementeren of verwijderen
#### [PowerShell](service-fabric-deploy-remove-applications.md)
#### [Visual Studio](service-fabric-publish-app-remote-cluster.md)
#### [FabricClient-API's](service-fabric-deploy-remove-applications-fabricclient.md)
### Een upgrade van een app uitvoeren
#### [Overzicht](service-fabric-application-upgrade.md)
#### [Toepassingsupgrade configureren](service-fabric-visualstudio-configure-upgrade.md)
#### [Parameters toepassingsupgrade](service-fabric-application-upgrade-parameters.md)
#### Upgraden
##### [PowerShell](service-fabric-application-upgrade-tutorial-powershell.md)
##### [Visual Studio](service-fabric-application-upgrade-tutorial.md)
#### [Problemen met toepassingsupgrades oplossen](service-fabric-application-upgrade-troubleshooting.md)
#### [Gegevensserialisatie in toepassingsupgrades](service-fabric-application-upgrade-data-serialization.md)
#### [Toepassingsupgrade: geavanceerde onderwerpen](service-fabric-application-upgrade-advanced.md)

### Testtoepassingen en -services
#### [Overzicht foutanalyse](service-fabric-testability-overview.md)
#### [Service-naar-servicecommunicatie testen](service-fabric-testability-scenarios-service-communication.md)
#### Fouten simuleren
##### [Gecontroleerde chaos gebruiken](service-fabric-controlled-chaos.md)
##### [Testacties gebruiken](service-fabric-testability-actions.md)
##### [Tijdens workloads](service-fabric-testability-workload-tests.md)
##### [Testscenario's gebruiken](service-fabric-testability-scenarios.md)
##### [De API's voor knooppuntovergang gebruiken](service-fabric-node-transition-apis.md)
#### [Uw testtoepassing laden](service-fabric-vso-load-test.md)

### Continue integratie instellen
#### [Continue integratie met VSTS instellen](service-fabric-set-up-continuous-integration.md)
#### [Uw Linux Java-app implementeren met behulp van Jenkins](service-fabric-cicd-your-linux-java-application-with-jenkins.md)

## Clusters maken en beheren

### [Overzicht](service-fabric-deploy-anywhere.md)
### Concepten
#### [Een cluster beschrijven](service-fabric-cluster-resource-manager-cluster-description.md)
#### [Clusterbeveiliging](service-fabric-cluster-security.md)
#### [Functieverschillen tussen Linux en Windows](service-fabric-linux-windows-differences.md)

### Plannen en voorbereiden
#### [Capaciteitsplanning](service-fabric-cluster-capacity.md)
#### [Herstel na noodgevallen](service-fabric-disaster-recovery.md)

### Clusters op Azure
#### Concepten
##### [Knooppunttypen en VM-schaalsets](service-fabric-cluster-nodetypes.md)
##### [Clusternetwerkpatronen](service-fabric-patterns-networking.md)
#### Maken 
##### [Azure Portal](service-fabric-cluster-creation-via-portal.md)
##### [Azure Resource Manager](service-fabric-cluster-creation-via-arm.md)
##### [Visual Studio en Azure Resource Manager](service-fabric-cluster-creation-via-visual-studio.md)
#### Schalen 
##### [Handmatig](service-fabric-cluster-scale-up-down.md)
##### [Programmatisch](service-fabric-cluster-programmatic-scaling.md)
#### [Upgraden](service-fabric-cluster-upgrade.md)
#### [Toegangsbeheer instellen](service-fabric-cluster-security-roles.md)
#### [Configureren](service-fabric-cluster-fabric-settings.md)
#### [Clustercertificaten beheren](service-fabric-cluster-security-update-certs-azure.md) 
#### [Verwijderen](service-fabric-cluster-delete.md)

### Zelfstandige clusters
#### [Implementatie plannen en voorbereiden](service-fabric-cluster-standalone-deployment-preparation.md)
#### Maken
##### [On-premises maken](service-fabric-cluster-creation-for-windows-server.md)
##### [Op virtuele machines in Azure maken](service-fabric-cluster-creation-with-windows-azure-vms.md)
##### [Beveiligen met behulp van certificaten](service-fabric-windows-cluster-x509-security.md)  
##### [Beveiligen met behulp van Windows-beveiliging](service-fabric-windows-cluster-windows-security.md)
##### [Inhoud van het zelfstandige pakket](service-fabric-cluster-standalone-package-contents.md)
#### [Schalen](service-fabric-cluster-windows-server-add-remove-nodes.md)
#### [Toegangsbeheer instellen](service-fabric-cluster-security-roles.md)
#### [Configureren](service-fabric-cluster-manifest.md)
#### [Upgraden](service-fabric-cluster-upgrade-windows-server.md) 

### [Een cluster visualiseren](service-fabric-visualizing-your-cluster.md)
### [Verbinding maken met een beveiligde cluster](service-fabric-connect-to-secure-cluster.md)

### [Een cluster beheren met Azure CLI](service-fabric-azure-cli.md)
### [Patch uitvoeren voor clusterknooppunten](service-fabric-patch-orchestration-application.md)

### Clusterbronnen beheren en organiseren
#### [Overzicht van Cluster Resource Manager](service-fabric-cluster-resource-manager-introduction.md)
#### [Cluster Resource Manager-architectuur](service-fabric-cluster-resource-manager-architecture.md)
#### [Een cluster beschrijven](service-fabric-cluster-resource-manager-cluster-description.md)
#### [Overzicht toepassingsgroepen](service-fabric-cluster-resource-manager-application-groups.md)
#### [Instellingen van Cluster Resource Manager configureren](service-fabric-cluster-resource-manager-configure-services.md)
#### [Bron metrische verbruiksgegevens](service-fabric-cluster-resource-manager-metrics.md)
#### [Serviceaffiniteit gebruiken](service-fabric-cluster-resource-manager-advanced-placement-rules-affinity.md)
#### [Beleid voor serviceplaatsing](service-fabric-cluster-resource-manager-advanced-placement-rules-placement-policies.md)
#### [Een cluster beheren](service-fabric-cluster-resource-manager-management-integration.md)
#### [Clusterdefragmentatie](service-fabric-cluster-resource-manager-defragmentation-metrics.md)
#### [Een cluster in balans brengen](service-fabric-cluster-resource-manager-balancing.md)
#### [Beperking](service-fabric-cluster-resource-manager-advanced-throttling.md)
#### [Servicebeweging](service-fabric-cluster-resource-manager-movement-cost.md)

## Bewaken en diagnoses uitvoeren
### [Toepassingen bewaken en er diagnoses op uitvoeren](service-fabric-diagnostics-overview.md)
### Gebeurtenissen genereren
#### [Gebeurtenissen op infrastructuurniveau genereren](service-fabric-diagnostics-event-generation-infra.md)
##### [Reliable Services-gebeurtenissen](service-fabric-reliable-services-diagnostics.md)
##### [Reliable Actors-gebeurtenissen](service-fabric-reliable-actors-diagnostics.md)
#### [Gebeurtenissen op toepassingsniveau genereren](service-fabric-diagnostics-event-generation-app.md)
### Status van toepassing en cluster inspecteren
#### [Service Fabric-status bewaken](service-fabric-health-introduction.md)
#### [Servicestatus rapporteren en controleren](service-fabric-diagnostics-how-to-report-and-check-service-health.md)
#### [Aangepaste statusrapporten toevoegen](service-fabric-report-health.md)
#### [Problemen met systeemstatusrapporten oplossen](service-fabric-understand-and-troubleshoot-with-system-health-reports.md)
#### [Statusrapporten weergeven](service-fabric-view-entities-aggregated-health.md)
### Gebeurtenissen samenstellen
#### [Gebeurtenissen samenstellen met EventFlow](service-fabric-diagnostics-event-aggregation-eventflow.md)
#### Gebeurtenissen samenstellen met Azure Diagnostics
##### [Windows](service-fabric-diagnostics-event-aggregation-wad.md)
##### [Linux](service-fabric-diagnostics-event-aggregation-lad.md)
### Gebeurtenissen analyseren
#### [Gebeurtenissen analyseren met Application Insights](service-fabric-diagnostics-event-analysis-appinsights.md)
#### [Gebeurtenissen analyseren met OMS](service-fabric-diagnostics-event-analysis-oms.md)
### [Problemen met uw lokale cluster oplossen](service-fabric-troubleshoot-local-cluster-setup.md)

# Naslaginformatie
## [PowerShell (Azure)](/powershell/module/azurerm.servicefabric/)
## [PowerShell](/powershell/azure/overview?view=azureservicefabricps)
## [Azure-CLI](/cli/azure/sf)
## [Java-API](/java/api/overview/azure/servicefabric)
## [.NET](/dotnet/api/overview/azure/servicefabric?view=azure-dotnet)
## [REST](/rest/api/servicefabric)

# Resources
## [Veelgestelde vragen over Service Fabric](service-fabric-common-questions.md)
## [Ondersteuningsopties voor Service Fabric](service-fabric-support.md)
## [Voorbeeldcode](http://aka.ms/servicefabricsamples)
## [Leertraject](https://azure.microsoft.com/documentation/learning-paths/service-fabric/)
## [Prijzen](https://azure.microsoft.com/pricing/details/service-fabric/)
## [Service-updates](https://azure.microsoft.com/updates/?product=service-fabric)
## [MSDN-forum](https://social.msdn.microsoft.com/Forums/home?forum=AzureServiceFabric)
## [Video's](https://azure.microsoft.com/documentation/videos/index/?services=service-fabric)
