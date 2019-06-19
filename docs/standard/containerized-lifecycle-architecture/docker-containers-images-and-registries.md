---
title: Контейнеры, образы и реестры Docker
description: Сведения о ключевой роли реестров при развертывании приложений в Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 7becadc3de16d96f8d6f167cf49c6cdd3bcc0d32
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "65641330"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="ece6c-103">Контейнеры, образы и реестры Docker</span><span class="sxs-lookup"><span data-stu-id="ece6c-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="ece6c-104">При использовании Docker вы создаете приложение или службу и упаковываете их и их зависимости в образ контейнера.</span><span class="sxs-lookup"><span data-stu-id="ece6c-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="ece6c-105">Образ — это статическое представление приложения или службы, а также их конфигурации и зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ece6c-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="ece6c-106">Для запуска приложения или службы создается экземпляр образа приложения, чтобы создать контейнер, который будет запущен на узле Docker.</span><span class="sxs-lookup"><span data-stu-id="ece6c-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="ece6c-107">Контейнеры изначально проверяются в среде разработки или на ПК.</span><span class="sxs-lookup"><span data-stu-id="ece6c-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="ece6c-108">Вам следует хранить образы в реестре, который выступает в качестве библиотеки образов.</span><span class="sxs-lookup"><span data-stu-id="ece6c-108">You store images in a registry, that acts as a library of images.</span></span> <span data-ttu-id="ece6c-109">Он необходим при развертывании на оркестраторы в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="ece6c-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="ece6c-110">Docker поддерживает общедоступный реестр с помощью [Docker Hub](https://hub.docker.com/). Другие поставщики предлагают реестры для различных коллекций образов, включая [Реестр контейнеров Azure](https://azure.microsoft.com/services/container-registry/).</span><span class="sxs-lookup"><span data-stu-id="ece6c-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="ece6c-111">Кроме того, организации могут развернуть локальные частные реестры для своих образов Docker.</span><span class="sxs-lookup"><span data-stu-id="ece6c-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="ece6c-112">На рисунке 1-4 показано, как образы и реестры в Docker связаны с другими компонентами.</span><span class="sxs-lookup"><span data-stu-id="ece6c-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="ece6c-113">На нем также показано несколько вариантов реестра от поставщиков.</span><span class="sxs-lookup"><span data-stu-id="ece6c-113">It also shows the multiple registry offerings from vendors.</span></span>

![Базовая таксономия в Docker. Реестр напоминает книжную полку. В нем хранятся образы, которые можно извлекать для создания контейнеров, необходимых для запуска служб или веб-приложений.](./media/image4.png)

<span data-ttu-id="ece6c-118">**Рис. 1-4**.</span><span class="sxs-lookup"><span data-stu-id="ece6c-118">**Figure 1-4**.</span></span> <span data-ttu-id="ece6c-119">Классификация основных понятий и терминов Docker</span><span class="sxs-lookup"><span data-stu-id="ece6c-119">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="ece6c-120">Размещение образов в реестре позволяет хранить статические и неизменяемые фрагменты приложений, включая все их зависимости на уровне платформы.</span><span class="sxs-lookup"><span data-stu-id="ece6c-120">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="ece6c-121">Затем эти образы можно добавить в систему управления версиями и развернуть в нескольких средах, создав таким образом согласованную единицу развертывания.</span><span class="sxs-lookup"><span data-stu-id="ece6c-121">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="ece6c-122">Частные реестры образов, размещенные локально или в облаке, рекомендуется использовать, если:</span><span class="sxs-lookup"><span data-stu-id="ece6c-122">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="ece6c-123">Ваши образы не могут быть открыты для общего доступа по соображениям конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="ece6c-123">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="ece6c-124">Вам необходимо обеспечить минимальную сетевую задержку между образами и выбранной средой развертывания.</span><span class="sxs-lookup"><span data-stu-id="ece6c-124">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="ece6c-125">Например, если рабочей средой является Azure, вы, вероятно, захотите разместить образы в [Реестре контейнеров Azure](https://azure.microsoft.com/services/container-registry/), чтобы сетевая задержка была минимальной.</span><span class="sxs-lookup"><span data-stu-id="ece6c-125">For example, if your production environment is Azure, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency is minimal.</span></span> <span data-ttu-id="ece6c-126">Точно так же, если рабочая среда является локальной, вы можете развернуть локальный доверенный реестр Docker в той же локальной сети.</span><span class="sxs-lookup"><span data-stu-id="ece6c-126">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ece6c-127">[Назад](docker-terminology.md)
>[Вперед](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="ece6c-127">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
