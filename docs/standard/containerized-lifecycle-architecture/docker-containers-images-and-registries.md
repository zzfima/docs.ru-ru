---
title: Контейнеры, образы и реестры Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 43b76f738fa4b7c89423a5b9fac7ef91f40880c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="b25ef-103">Контейнеры, образы и реестры Docker</span><span class="sxs-lookup"><span data-stu-id="b25ef-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="b25ef-104">При использовании Docker, вы создаете приложения или службы и пакета его и его зависимости в образ контейнера.</span><span class="sxs-lookup"><span data-stu-id="b25ef-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="b25ef-105">Образ — это статическое представление приложения или службы, а также их конфигурации и зависимостей.</span><span class="sxs-lookup"><span data-stu-id="b25ef-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="b25ef-106">Для выполнения приложения или службы, чтобы создать контейнер, в котором будут выполняться на узле Docker создается образ приложения.</span><span class="sxs-lookup"><span data-stu-id="b25ef-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="b25ef-107">Контейнеры изначально проверяются в среде разработки или на ПК.</span><span class="sxs-lookup"><span data-stu-id="b25ef-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="b25ef-108">Хранятся в реестре, который выступает в качестве библиотеки образов изображения.</span><span class="sxs-lookup"><span data-stu-id="b25ef-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="b25ef-109">При развертывании в рабочей среде orchestrators необходимо реестра.</span><span class="sxs-lookup"><span data-stu-id="b25ef-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="b25ef-110">Docker поддерживает общедоступный реестр с помощью [Центра Docker](https://hub.docker.com/); другие поставщики предлагают реестры для различных коллекций образов.</span><span class="sxs-lookup"><span data-stu-id="b25ef-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="b25ef-111">Кроме того, организации могут развернуть локальные частные реестры для своих образов Docker.</span><span class="sxs-lookup"><span data-stu-id="b25ef-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="b25ef-112">На рис. 1-4 показано, как изображения и реестров в Docker связаны с другими компонентами.</span><span class="sxs-lookup"><span data-stu-id="b25ef-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="b25ef-113">На нем также показано несколько вариантов реестра от поставщиков.</span><span class="sxs-lookup"><span data-stu-id="b25ef-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="b25ef-114">Рисунок 1-4: классификация Docker термины и основные понятия</span><span class="sxs-lookup"><span data-stu-id="b25ef-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="b25ef-115">Поместив изображения в реестре, можно хранить разряды статические и неизменяемый приложения, включая все их зависимости на уровне framework.</span><span class="sxs-lookup"><span data-stu-id="b25ef-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="b25ef-116">Вы затем можно версии и развертывания образов в нескольких средах и таким образом предоставляют единицу развертывания.</span><span class="sxs-lookup"><span data-stu-id="b25ef-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="b25ef-117">Реестры частный образ размещается локально или в облаке, рекомендуется использовать в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="b25ef-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="b25ef-118">Ваши образы не могут быть открыты для общего доступа по соображениям конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="b25ef-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="b25ef-119">Вам необходимо обеспечить минимальную сетевую задержку между образами и выбранной средой развертывания.</span><span class="sxs-lookup"><span data-stu-id="b25ef-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="b25ef-120">Например если вашей рабочей среде Azure, может потребоваться хранения рисунков в реестре контейнера Azure, чтобы сетевая задержка будет минимальной.</span><span class="sxs-lookup"><span data-stu-id="b25ef-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="b25ef-121">Точно так же, если рабочая среда является локальной, вы можете развернуть локальный доверенный реестр Docker в той же локальной сети.</span><span class="sxs-lookup"><span data-stu-id="b25ef-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b25ef-122">[Предыдущие] docker (terminology.md) [Далее] (Docker приложения-жизненного цикла/index.md)</span><span class="sxs-lookup"><span data-stu-id="b25ef-122">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
