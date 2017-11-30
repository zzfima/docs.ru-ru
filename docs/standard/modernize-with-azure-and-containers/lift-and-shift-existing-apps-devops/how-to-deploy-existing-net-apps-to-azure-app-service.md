---
title: "Развертывание существующего приложения .NET для службы приложений Azure"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Развертывание существующего приложения .NET для службы приложений Azure"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: c83703c6f3dede0f92263e0d46bf48525c3eefaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="c6eae-103">Развертывание существующего приложения .NET для службы приложений Azure</span><span class="sxs-lookup"><span data-stu-id="c6eae-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="c6eae-104">Компонент веб-приложениях службы приложений Azure — это полностью управляемая вычислений платформа, которая оптимизирована для размещения веб-сайтов и веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="c6eae-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="c6eae-105">Это предложение PaaS в Microsoft Azure позволяет вам сосредоточиться на бизнес-логики, пока Azure заботится инфраструктуры для запуска и масштабирования приложения.</span><span class="sxs-lookup"><span data-stu-id="c6eae-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="c6eae-106">Проверки узлов и перенести в службу приложений с помощью помощника по миграции Azure приложения службы</span><span class="sxs-lookup"><span data-stu-id="c6eae-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="c6eae-107">При создании нового приложения в Visual Studio, перемещение приложение службы приложений обычно достаточно прост.</span><span class="sxs-lookup"><span data-stu-id="c6eae-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="c6eae-108">Тем не менее если вы планируете миграцию существующего приложения службы приложений, сначала необходимо проверить совместимость со службой приложения все зависимости приложения от.</span><span class="sxs-lookup"><span data-stu-id="c6eae-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="c6eae-109">Сюда входят зависимости, такие как операционной системы и сторонних разработчиков программного обеспечения, установленного на сервере.</span><span class="sxs-lookup"><span data-stu-id="c6eae-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="c6eae-110">Можно использовать [помощник по миграции Azure приложение службы](https://www.migratetoazure.net/) для анализа сайтов и затем перенести их с веб-серверов Windows и Linux в службу приложений.</span><span class="sxs-lookup"><span data-stu-id="c6eae-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="c6eae-111">В процессе миграции средство создает веб-приложений и баз данных в Azure по мере необходимости публиковать содержимое и публикует базы данных.</span><span class="sxs-lookup"><span data-stu-id="c6eae-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="c6eae-112">Azure приложение службы помощник по миграции поддерживает миграцию с IIS, работающем на Windows Server в облако.</span><span class="sxs-lookup"><span data-stu-id="c6eae-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="c6eae-113">Службы приложений поддерживает Windows Server 2003 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c6eae-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.NET/Images/ImageCanvas.PNG](./media/image5.png)
>
> <span data-ttu-id="c6eae-115">**Рис. 4-5.**</span><span class="sxs-lookup"><span data-stu-id="c6eae-115">**Figure 4-5.**</span></span> <span data-ttu-id="c6eae-116">Используя помощник по миграции службы приложений Azure</span><span class="sxs-lookup"><span data-stu-id="c6eae-116">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="c6eae-117">Приложение службы помощник по миграции — это средство, перемещает веб-сайты из веб-серверов в облаке Azure.</span><span class="sxs-lookup"><span data-stu-id="c6eae-117">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="c6eae-118">После миграции для служб приложений веб-сайта на сайте имеются все необходимое для запуска безопасно и эффективно.</span><span class="sxs-lookup"><span data-stu-id="c6eae-118">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="c6eae-119">Узлы настраиваются и автоматический запуск в облаке Azure PaaS (служба приложений).</span><span class="sxs-lookup"><span data-stu-id="c6eae-119">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="c6eae-120">Средство миграции служб приложений можно анализировать веб-сайтов и отчетов по их совместимости для перемещения в службу приложений.</span><span class="sxs-lookup"><span data-stu-id="c6eae-120">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="c6eae-121">Если вы довольны анализа, можно позволить приложения службы помощник по миграции перенести содержимое, данных и параметров для вас.</span><span class="sxs-lookup"><span data-stu-id="c6eae-121">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="c6eae-122">Если сайта довольно несовместима, средства миграции показывает, что необходимо настроить для работы.</span><span class="sxs-lookup"><span data-stu-id="c6eae-122">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c6eae-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c6eae-123">Additional resources</span></span>

-   <span data-ttu-id="c6eae-124">**Помощник по миграции службы приложений Azure**</span><span class="sxs-lookup"><span data-stu-id="c6eae-124">**Azure App Service Migration Assistant**</span></span>

    [<span data-ttu-id="c6eae-125">https://www.migratetoazure.NET/</span><span class="sxs-lookup"><span data-stu-id="c6eae-125">https://www.migratetoazure.net/</span></span>](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="c6eae-126">[Назад](what-about-cloud-optimized-applications.md)
[Вперед](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="c6eae-126">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>
