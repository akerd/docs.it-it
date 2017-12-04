---
title: "Orchestrazione di microservizi e le applicazioni multi-contenitore per la scalabilità e disponibilità elevate"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Orchestrazione di microservizi e le applicazioni multi-contenitore per la scalabilità e disponibilità elevate"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a><span data-ttu-id="0bbbc-104">Orchestrazione di microservizi e le applicazioni multi-contenitore per la scalabilità e disponibilità elevate</span><span class="sxs-lookup"><span data-stu-id="0bbbc-104">Orchestrating microservices and multi-container applications for high scalability and availability</span></span>

<span data-ttu-id="0bbbc-105">Utilizzare orchestrators per le applicazioni di ambiente di produzione è essenziale se l'applicazione è basata sul microservizi o semplicemente suddivisi tra più contenitori.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-105">Using orchestrators for production-ready applications is essential if your application is based on microservices or simply split across multiple containers.</span></span> <span data-ttu-id="0bbbc-106">Come descritto in precedenza, in un approccio basato su microservizio, ogni microservizio possiede il modello e i dati in modo che sia di un punto di vista di distribuzione e sviluppo.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-106">As introduced previously, in a microservice-based approach, each microservice owns its model and data so that it will be autonomous from a development and deployment point of view.</span></span> <span data-ttu-id="0bbbc-107">Tuttavia, anche se si dispone di un'applicazione più tradizionale è costituito da più servizi (ad esempio SOA), si disporrà di più contenitori o servizi che comprendono un'applicazione di business che devono essere distribuiti come un sistema distribuito.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-107">But even if you have a more traditional application that is composed of multiple services (like SOA), you will also have multiple containers or services comprising a single business application that need to be deployed as a distributed system.</span></span> <span data-ttu-id="0bbbc-108">Questi tipi di sistemi sono complessi di scalabilità orizzontale e gestire; Pertanto, è indispensabile agente di orchestrazione se si desidera disporre di un'applicazione contenitore più ambienti di produzione e scalabile.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-108">These kinds of systems are complex to scale out and manage; therefore, you absolutely need an orchestrator if you want to have a production-ready and scalable multi-container application.</span></span>

<span data-ttu-id="0bbbc-109">Figura 4-23 illustra la distribuzione in un cluster di un'applicazione composta da più microservizi (contenitori).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-109">Figure 4-23 illustrates deployment into a cluster of an application composed of multiple microservices (containers).</span></span>

![](./media/image23.PNG)

<span data-ttu-id="0bbbc-110">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-110">**Figure 4-23**.</span></span> <span data-ttu-id="0bbbc-111">Un cluster di contenitori</span><span class="sxs-lookup"><span data-stu-id="0bbbc-111">A cluster of containers</span></span>

<span data-ttu-id="0bbbc-112">Si differenzia da un approccio logico.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-112">It looks like a logical approach.</span></span> <span data-ttu-id="0bbbc-113">Ma, come bilanciamento carico di gestione, routing e la coordinazione questi composte da applicazioni?</span><span class="sxs-lookup"><span data-stu-id="0bbbc-113">But how are you handling load-balancing, routing, and orchestrating these composed applications?</span></span>

<span data-ttu-id="0bbbc-114">Il motore Docker normale negli host Docker singolo soddisfa le esigenze di gestire le istanze di singola immagine in un host, ma ricadere breve per quanto riguarda la gestione dei contenitori più distribuiti su più host per le applicazioni distribuite complesse.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-114">The plain Docker Engine in single Docker hosts meets the needs of managing single image instances on one host, but it falls short when it comes to managing multiple containers deployed on multiple hosts for more complex distributed applications.</span></span> <span data-ttu-id="0bbbc-115">Nella maggior parte dei casi, è necessario una piattaforma di gestione che verrà automaticamente contenitori, i contenitori di scalabilità orizzontale con più istanze per ogni immagine di avvio, sospenderli o spegnerle quando necessario e idealmente inoltre controllare la modalità con cui accedono alle risorse come la rete e i dati spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-115">In most cases, you need a management platform that will automatically start containers, scale-out containers with multiple instances per image, suspend them or shut them down when needed, and ideally also control how they access resources like the network and data storage.</span></span>

<span data-ttu-id="0bbbc-116">Per andare oltre la gestione dei singoli contenitori o le app di comporre molto semplice e spostamento verso più grandi applicazioni aziendali con microservizi, è necessario attivare di orchestrazione e al clustering di piattaforme.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-116">To go beyond the management of individual containers or very simple composed apps and move toward larger enterprise applications with microservices, you must turn to orchestration and clustering platforms.</span></span>

<span data-ttu-id="0bbbc-117">Da un'architettura e sviluppo punto di vista, se si sta compilando una grande impresa costituita da applicazioni basate su microservizi, è importante comprendere le piattaforme e i prodotti che supportano scenari avanzati seguenti:</span><span class="sxs-lookup"><span data-stu-id="0bbbc-117">From an architecture and development point of view, if you are building large enterprise composed of microservices-based applications, it is important to understand the following platforms and products that support advanced scenarios:</span></span>

<span data-ttu-id="0bbbc-118">**I cluster e orchestrators**.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-118">**Clusters and orchestrators**.</span></span> <span data-ttu-id="0bbbc-119">Quando è necessario scalare orizzontalmente le applicazioni attraverso numerosi host Docker, come quando un'applicazione basata su microservizio grandi dimensioni, è importante essere in grado di gestire tutti gli host come un singolo cluster mediante l'astrazione della complessità della piattaforma sottostante.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-119">When you need to scale out applications across many Docker hosts, as when a large microservice-based application, it is critical to be able to manage all those hosts as a single cluster by abstracting the complexity of the underlying platform.</span></span> <span data-ttu-id="0bbbc-120">Che rappresenta il cluster di contenitore e orchestrators fornire.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-120">That is what the container clusters and orchestrators provide.</span></span> <span data-ttu-id="0bbbc-121">Esempi di orchestrators sono Azure Service Fabric, Kubernetes, Docker Swarm e Mesosphere controller di dominio o sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-121">Examples of orchestrators are Azure Service Fabric, Kubernetes, Docker Swarm and Mesosphere DC/OS.</span></span> <span data-ttu-id="0bbbc-122">Le ultime tre orchestrators open source disponibili in Azure tramite il servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-122">The last three open-source orchestrators are available in Azure through Azure Container Service.</span></span>

<span data-ttu-id="0bbbc-123">**Utilità di pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-123">**Schedulers**.</span></span> <span data-ttu-id="0bbbc-124">*Pianificazione* significa avere la funzionalità di un amministratore per avviare i contenitori in un cluster in modo oltre a fornire un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-124">*Scheduling* means to have the capability for an administrator to launch containers in a cluster so they also provide a UI.</span></span> <span data-ttu-id="0bbbc-125">Un'utilità di pianificazione di cluster con responsabilità diverse: da usare in modo efficiente le risorse del cluster, per impostare i vincoli forniti dall'utente, ai contenitori di bilanciamento del carico in modo efficiente tra nodi o host e affidabile per dagli errori fornendo alto disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-125">A cluster scheduler has several responsibilities: to use the cluster’s resources efficiently, to set the constraints provided by the user, to efficiently load-balance containers across nodes or hosts, and to be robust against errors while providing high availability.</span></span>

<span data-ttu-id="0bbbc-126">I concetti di un cluster e un'utilità di pianificazione sono strettamente correlati, pertanto i prodotti disponibili da fornitori diversi spesso forniscono entrambi i set di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-126">The concepts of a cluster and a scheduler are closely related, so the products provided by different vendors often provide both sets of capabilities.</span></span> <span data-ttu-id="0bbbc-127">Nell'elenco seguente viene illustrata la piattaforma più importante e scelte di software che disponibili per i cluster e le utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-127">The following list shows the most important platform and software choices you have for clusters and schedulers.</span></span> <span data-ttu-id="0bbbc-128">Questi orchestrators sono in genere disponibili in cloud pubblici, come Azure.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-128">These orchestrators are generally offered in public clouds like Azure.</span></span>

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a><span data-ttu-id="0bbbc-129">Piattaforme software per il clustering di contenitore, orchestrazione e la pianificazione</span><span class="sxs-lookup"><span data-stu-id="0bbbc-129">Software platforms for container clustering, orchestration, and scheduling</span></span>

<span data-ttu-id="0bbbc-130">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="0bbbc-130">Kubernetes</span></span>

![https://PBS.twimg.com/Media/BT\_pEfqCAAAiVyz.png](./media/image24.png)

> <span data-ttu-id="0bbbc-132">Kubernetes è un prodotto open source che offre funzionalità che è compreso tra l'infrastruttura di cluster e il contenitore di programmazione alle funzionalità di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-132">Kubernetes is an open-source product that provides functionality that ranges from cluster infrastructure and container scheduling to orchestrating capabilities.</span></span> <span data-ttu-id="0bbbc-133">Consente di automatizzare la distribuzione, ridimensionamento e delle operazioni di contenitori di applicazioni per i cluster di host.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-133">It lets you automate deployment, scaling, and operations of application containers across clusters of hosts.</span></span>
>
> <span data-ttu-id="0bbbc-134">Kubernetes fornisce un'infrastruttura incentrato sul contenitore che raggruppa i contenitori di applicazioni in unità logiche per facilità di gestione e l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-134">Kubernetes provides a container-centric infrastructure that groups application containers into logical units for easy management and discovery.</span></span>
>
> <span data-ttu-id="0bbbc-135">Kubernetes è obsoleta in Linux, è meno avanzata in Windows.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-135">Kubernetes is mature in Linux, less mature in Windows.</span></span>

<span data-ttu-id="0bbbc-136">Sciame docker</span><span class="sxs-lookup"><span data-stu-id="0bbbc-136">Docker Swarm</span></span>

![http://rancher.com/WP-Content/Themes/rancher-2016/Assets/Images/Swarm.PNG?v=2016-07-10-AM](./media/image25.png)

> <span data-ttu-id="0bbbc-138">Docker sciame consente di pianificare i contenitori di Docker e del cluster.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-138">Docker Swarm lets you cluster and schedule Docker containers.</span></span> <span data-ttu-id="0bbbc-139">Utilizzando sciame, è possibile trasformare un pool di host Docker in un singolo host Docker virtuale.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-139">By using Swarm, you can turn a pool of Docker hosts into a single, virtual Docker host.</span></span> <span data-ttu-id="0bbbc-140">I client possono effettuare le richieste di API per Swarm esattamente come che avviene per gli host, vale a dire che sciame consente alle applicazioni di adattarsi a più host.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-140">Clients can make API requests to Swarm the same way they do to hosts, meaning that Swarm makes it easy for applications to scale to multiple hosts.</span></span>
>
> <span data-ttu-id="0bbbc-141">Sciame docker è un prodotto da Docker, la società.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-141">Docker Swarm is a product from Docker, the company.</span></span>
>
> <span data-ttu-id="0bbbc-142">V 1.12 docker o in un secondo momento eseguire modalità nativa e incorporati Swarm.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-142">Docker v1.12 or later can run native and built-in Swarm Mode.</span></span>

<span data-ttu-id="0bbbc-143">Controller di dominio mesosphere/OS</span><span class="sxs-lookup"><span data-stu-id="0bbbc-143">Mesosphere DC/OS</span></span>

![https://mesosphere.com/wp-content/uploads/2016/04/logo-Horizontal-Styled.PNG](./media/image26.png)

> <span data-ttu-id="0bbbc-145">Mesosphere Enterprise DC/OS (basato su Apache Mesos) è una piattaforma di ambiente di produzione per l'esecuzione di contenitori e le applicazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-145">Mesosphere Enterprise DC/OS (based on Apache Mesos) is a production-ready platform for running containers and distributed applications.</span></span>
>
> <span data-ttu-id="0bbbc-146">Controller di dominio/OS funziona tramite l'astrazione di una raccolta di risorse disponibili nel cluster e rendere tali risorse disponibili per i componenti compilati su di esso.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-146">DC/OS works by abstracting a collection of the resources available in the cluster and making those resources available to components built on top of it.</span></span> <span data-ttu-id="0bbbc-147">Maratona viene in genere utilizzato come un'utilità di pianificazione integrata con controller di dominio o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-147">Marathon is usually used as a scheduler integrated with DC/OS.</span></span>
>
> <span data-ttu-id="0bbbc-148">Controller di dominio o sistema operativo è avanzata in Linux, è meno avanzata in Windows.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-148">DC/OS is mature in Linux, less mature in Windows.</span></span>

<span data-ttu-id="0bbbc-149">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="0bbbc-149">Azure Service Fabric</span></span>

![https://Azure.microsoft.com/svghandler/Service-fabric?Width=600&Height=315](./media/image27.png)

> <span data-ttu-id="0bbbc-151">[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-151">[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) is a Microsoft microservices platform for building applications.</span></span> <span data-ttu-id="0bbbc-152">Si tratta di un [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e creato un cluster di macchine.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-152">It is an [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) of services and creates clusters of machines.</span></span> <span data-ttu-id="0bbbc-153">Service Fabric è possibile distribuire servizi come contenitori o processi normali.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-153">Service Fabric can deploy services as containers or as plain processes.</span></span> <span data-ttu-id="0bbbc-154">È possibile anche combinazione servizi nei processi con i servizi in contenitori all'interno della stessa applicazione e del cluster.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-154">It can even mix services in processes with services in containers within the same application and cluster.</span></span>
>
> <span data-ttu-id="0bbbc-155">Service Fabric fornisce aggiuntive e facoltative rigorosa [modelli di programmazione di Service Fabric ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) come [servizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-155">Service Fabric provides additional and optional prescriptive [Service Fabric programming models ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) like [stateful services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) and [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).</span></span>
>
> <span data-ttu-id="0bbbc-156">Service Fabric è avanzata in Windows (anni evoluzione di Windows), meno avanzata in Linux.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-156">Service Fabric is mature in Windows (years evolving in Windows), less mature in Linux.</span></span> 
> <span data-ttu-id="0bbbc-157">Contenitori di Linux e Windows sono supportati in Service Fabric dal 2017.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-157">Both Linux and Windows containers are supported in Service Fabric since 2017.</span></span>

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a><span data-ttu-id="0bbbc-158">Utilizzo di orchestrators basate sul contenitore in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="0bbbc-158">Using container-based orchestrators in Microsoft Azure</span></span>

<span data-ttu-id="0bbbc-159">Diversi fornitori di cloud offrono il supporto di contenitori di Docker più cluster Docker e supporto di orchestrazione, tra cui Microsoft Azure, servizio di Amazon EC2 contenitore e il motore di contenitore di Google.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-159">Several cloud vendors offer Docker containers support plus Docker clusters and orchestration support, including Microsoft Azure, Amazon EC2 Container Service, and Google Container Engine.</span></span> <span data-ttu-id="0bbbc-160">Microsoft Azure supporta Docker cluster e orchestrator tramite servizio contenitore di Azure (ACS), come illustrato nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-160">Microsoft Azure provides Docker cluster and orchestrator support through Azure Container Service (ACS), as explained in the next section.</span></span>

<span data-ttu-id="0bbbc-161">Un'altra opzione consiste nell'usare Microsoft Azure Service Fabric (un microservizi platform), che supporta anche Docker basato sui contenitori di Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-161">Another choice is to use Microsoft Azure Service Fabric (a microservices platform), which also supports Docker based on Linux and Windows Containers.</span></span> <span data-ttu-id="0bbbc-162">Service Fabric in esecuzione in Azure o qualsiasi altro cloud ed esegue anche [locale](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-162">Service Fabric runs on Azure or any other cloud, and also runs [on-premises](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).</span></span>

## <a name="using-azure-container-service"></a><span data-ttu-id="0bbbc-163">Tramite il servizio contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="0bbbc-163">Using Azure Container Service</span></span>

<span data-ttu-id="0bbbc-164">Un cluster di Docker pool più host Docker e li espone come un unico host Docker virtuale, pertanto è possibile distribuire più contenitori nel cluster.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-164">A Docker cluster pools multiple Docker hosts and exposes them as a single virtual Docker host, so you can deploy multiple containers into the cluster.</span></span> <span data-ttu-id="0bbbc-165">Il cluster consente di gestire tutte le funzionalità di gestione complesse, quali la scalabilità, integrità e così via.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-165">The cluster will handle all the complex management plumbing, like scalability, health, and so forth.</span></span> <span data-ttu-id="0bbbc-166">Figura 4-24 rappresenta la modalità di mapping per servizio contenitore di Azure (ACS) in un cluster di Docker per comporre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-166">Figure 4-24 represents how a Docker cluster for composed applications maps to Azure Container Service (ACS).</span></span>

<span data-ttu-id="0bbbc-167">ACS fornisce un modo per semplificare la creazione, configurazione e gestione di un cluster di macchine virtuali che sono preconfigurati per l'esecuzione di applicazioni nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-167">ACS provides a way to simplify the creation, configuration, and management of a cluster of virtual machines that are preconfigured to run containerized applications.</span></span> <span data-ttu-id="0bbbc-168">Ottimizzare la configurazione di strumenti di pianificazione e l'orchestrazione open source più diffusi, ACS consente di usare le competenze esistenti o creare un corpo elevato e crescente di esperienza della community per distribuire e gestire applicazioni basate sul contenitore in Microsoft Azure .</span><span class="sxs-lookup"><span data-stu-id="0bbbc-168">Using an optimized configuration of popular open-source scheduling and orchestration tools, ACS enables you to use your existing skills or draw on a large and growing body of community expertise to deploy and manage container-based applications on Microsoft Azure.</span></span>

<span data-ttu-id="0bbbc-169">Il servizio contenitore di Azure consente di ottimizzare la configurazione di comuni strumenti di Docker clustering open source e tecnologie in modo specifico per Azure.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-169">Azure Container Service optimizes the configuration of popular Docker clustering open source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="0bbbc-170">È possibile ottenere una soluzione aperta che offre la portabilità per i contenitori e configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-170">You get an open solution that offers portability for both your containers and your application configuration.</span></span> <span data-ttu-id="0bbbc-171">Si seleziona la dimensione, il numero di host e gli strumenti di orchestrator e il servizio contenitore gestisce tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-171">You select the size, the number of hosts, and the orchestrator tools, and Container Service handles everything else.</span></span>

![](./media/image28.png)

<span data-ttu-id="0bbbc-172">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-172">**Figure 4-24**.</span></span> <span data-ttu-id="0bbbc-173">Clustering scelte contenitore nel servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="0bbbc-173">Clustering choices in Azure Container Service</span></span>

<span data-ttu-id="0bbbc-174">ACS sfrutta le immagini Docker per assicurarsi che i contenitori di applicazioni siano completamente portabili.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-174">ACS leverages Docker images to ensure that your application containers are fully portable.</span></span> <span data-ttu-id="0bbbc-175">Supporta la scelta delle piattaforme open source orchestrazione come controller di dominio o del sistema operativo (con tecnologia Mesos Apache), Kubernetes (originariamente creato da Google) e Docker Swarm, per garantire che queste applicazioni possono essere ridimensionate a migliaia o persino decine di migliaia di contenitori.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-175">It supports your choice of open-source orchestration platforms like DC/OS (powered by Apache Mesos), Kubernetes (originally created by Google), and Docker Swarm, to ensure that these applications can be scaled to thousands or even tens of thousands of containers.</span></span>

<span data-ttu-id="0bbbc-176">Il servizio contenitore di Azure consente di sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-176">The Azure Container service enables you to take advantage of the enterprise-grade features of Azure while still maintaining application portability, including at the orchestration layers.</span></span>

![](./media/image29.png)

<span data-ttu-id="0bbbc-177">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-177">**Figure 4-25**.</span></span> <span data-ttu-id="0bbbc-178">Orchestrators in ACS</span><span class="sxs-lookup"><span data-stu-id="0bbbc-178">Orchestrators in ACS</span></span>

<span data-ttu-id="0bbbc-179">Come illustrato nella figura 4-25, il servizio contenitore di Azure è semplicemente l'infrastruttura fornita da Azure per distribuire i controller di dominio/OS, Kubernetes o Docker Swarm, ma ACS non implementa alcun orchestrator aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-179">As shown in Figure 4-25, Azure Container Service is simply the infrastructure provided by Azure in order to deploy DC/OS, Kubernetes or Docker Swarm, but ACS does not implement any additional orchestrator.</span></span> <span data-ttu-id="0bbbc-180">Pertanto, ACS non è un agente di orchestrazione di conseguenza, solo un'infrastruttura che sfrutta esistente orchestrators open source per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-180">Therefore, ACS is not an orchestrator as such, only an infrastructure that leverages existing open-source orchestrators for containers.</span></span>

<span data-ttu-id="0bbbc-181">Dal punto di vista dell'utilizzo, l'obiettivo di servizio di contenitore di Azure è fornire un ambiente host del contenitore usando tecnologie e strumenti open source più diffusi.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-181">From a usage perspective, the goal of Azure Container Service is to provide a container hosting environment by using popular open-source tools and technologies.</span></span> <span data-ttu-id="0bbbc-182">A tal fine, che espone gli endpoint API standard per la scelta orchestrator.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-182">To this end, it exposes the standard API endpoints for your chosen orchestrator.</span></span> <span data-ttu-id="0bbbc-183">Tramite questi endpoint, è possibile utilizzare qualsiasi software in grado di comunicare con gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-183">By using these endpoints, you can leverage any software that can talk to those endpoints.</span></span> <span data-ttu-id="0bbbc-184">Ad esempio, nel caso l'endpoint Docker Swarm, è possibile utilizzare l'interfaccia della riga di comando di Docker (CLI).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-184">For example, in the case of the Docker Swarm endpoint, you might choose to use the Docker command-line interface (CLI).</span></span> <span data-ttu-id="0bbbc-185">Per controller di dominio o del sistema operativo, è possibile scegliere di utilizzare l'interfaccia CLI di controller di dominio o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-185">For DC/OS, you might choose to use the DC/OS CLI.</span></span>

### <a name="getting-started-with-azure-container-service"></a><span data-ttu-id="0bbbc-186">Introduzione al servizio di contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="0bbbc-186">Getting started with Azure Container Service</span></span> 

<span data-ttu-id="0bbbc-187">Per iniziare a utilizzare il servizio contenitore di Azure, si distribuisce un cluster il servizio contenitore di Azure dal portale di Azure utilizzando un modello di gestione risorse di Azure o [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-187">To begin using Azure Container Service, you deploy an Azure Container Service cluster from the Azure portal by using an Azure Resource Manager template or the [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli).</span></span> <span data-ttu-id="0bbbc-188">I modelli disponibili includono [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), e [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-188">Available templates include [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), and [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos).</span></span> <span data-ttu-id="0bbbc-189">Per includere la configurazione di Azure aggiuntiva o avanzata, è possono modificare i modelli di avvio rapido.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-189">The quickstart templates can be modified to include additional or advanced Azure configuration.</span></span> <span data-ttu-id="0bbbc-190">Per ulteriori informazioni sulla distribuzione di un cluster il servizio contenitore di Azure, vedere [distribuire un cluster il servizio contenitore di Azure](https://docs.microsoft.com/azure/container-service/container-service-deployment) sul sito Web di Azure.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-190">For more information on deploying an Azure Container Service cluster, see [Deploy an Azure Container Service cluster](https://docs.microsoft.com/azure/container-service/container-service-deployment) on the Azure website.</span></span>

<span data-ttu-id="0bbbc-191">Sono non state tariffe per tutti i software installati per impostazione predefinita come parte del servizio ACS.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-191">There are no fees for any of the software installed by default as part of ACS.</span></span> <span data-ttu-id="0bbbc-192">Tutte le opzioni predefinite sono implementate con software open source.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-192">All default options are implemented with open-source software.</span></span>

<span data-ttu-id="0bbbc-193">ACS è attualmente disponibile per la serie di Standard A, D, DS, G e GS macchine virtuali Linux in Azure.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-193">ACS is currently available for Standard A, D, DS, G, and GS series Linux virtual machines in Azure.</span></span> <span data-ttu-id="0bbbc-194">Viene addebitato solo per le istanze di calcolo che si sceglie, nonché altri infrastruttura risorse sottostanti utilizzate, ad esempio l'archiviazione e rete.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-194">You are charged only for the compute instances you choose, as well as the other underlying infrastructure resources consumed, such as storage and networking.</span></span> <span data-ttu-id="0bbbc-195">Non sono previsti costi incrementali per ACS se stesso.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-195">There are no incremental charges for ACS itself.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bbbc-196">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0bbbc-196">Additional resources</span></span>

-   <span data-ttu-id="0bbbc-197">**Introduzione a soluzioni con il servizio contenitore di Azure contenitore Docker**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)</span><span class="sxs-lookup"><span data-stu-id="0bbbc-197">**Introduction to Docker container hosting solutions with Azure Container Service**
[*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)</span></span>

-   <span data-ttu-id="0bbbc-198">**Panoramica di docker sciame**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)</span><span class="sxs-lookup"><span data-stu-id="0bbbc-198">**Docker Swarm overview**
[*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)</span></span>

-   <span data-ttu-id="0bbbc-199">**Panoramica sulla modalità di Swarm**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)</span><span class="sxs-lookup"><span data-stu-id="0bbbc-199">**Swarm mode overview**
[*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)</span></span>

-   <span data-ttu-id="0bbbc-200">**Panoramica di controller di dominio/OS mesosphere**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)</span><span class="sxs-lookup"><span data-stu-id="0bbbc-200">**Mesosphere DC/OS Overview**
[*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)</span></span>

-   <span data-ttu-id="0bbbc-201">**Kubernetes.**</span><span class="sxs-lookup"><span data-stu-id="0bbbc-201">**Kubernetes.**</span></span> <span data-ttu-id="0bbbc-202">Il sito ufficiale. \\</span><span class="sxs-lookup"><span data-stu-id="0bbbc-202">The official site.\\</span></span>
    [<span data-ttu-id="0bbbc-203">*http://kubernetes.IO/*</span><span class="sxs-lookup"><span data-stu-id="0bbbc-203">*http://kubernetes.io/*</span></span>](http://kubernetes.io/)


>[!div class="step-by-step"]
<span data-ttu-id="0bbbc-204">[Precedente] (resilienti-elevata-disponibilità-microservices.md) [Avanti] (con-azure-servizio-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="0bbbc-204">[Previous] (resilient-high-availability-microservices.md) [Next] (using-azure-service-fabric.md)</span></span>