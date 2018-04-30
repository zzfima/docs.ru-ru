---
title: Руководство по миграции
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e6b42296d6780d93d5835b89732d114de6d8aca
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="migration-guidance"></a><span data-ttu-id="d8925-102">Руководство по миграции</span><span class="sxs-lookup"><span data-stu-id="d8925-102">Migration Guidance</span></span>
<span data-ttu-id="d8925-103">В [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], корпорация Майкрософт выпускает вторую основную версию Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="d8925-103">In the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], Microsoft is releasing the second major version of Windows Workflow Foundation (WF).</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="d8925-104"> была выпущена в составе [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (она включала типы в пространствах имен System.Workflow.\*, которые теперь называются WF3) и улучшена в [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8925-104"> was released in [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (this included the types in the System.Workflow.\* namespaces; now referred to as WF3) and enhanced in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="d8925-105">WF3 также является частью [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], но он сосуществует с новой технологией рабочего процесса (типы в System.Activities.\* пространств имен; называются WF4).</span><span class="sxs-lookup"><span data-stu-id="d8925-105">WF3 is also part of the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], but it exists there alongside new workflow technology (the types in the System.Activities.\* namespaces; referred to as WF4).</span></span> <span data-ttu-id="d8925-106">При принятии решения об использовании WF4 важно помнить, что управление временем осуществляет пользователь.</span><span class="sxs-lookup"><span data-stu-id="d8925-106">When considering when to adopt WF4, it is important to first recognize that you control the timing.</span></span>  
  
-   <span data-ttu-id="d8925-107">WF3 представляет собой полностью поддерживаемую часть [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8925-107">WF3 is a fully supported part of the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="d8925-108">Приложения WF3 запускаются в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] без внесения изменений, при этом они по-прежнему полностью поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d8925-108">WF3 applications run on the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] without modification and continue to be fully supported.</span></span>  
  
-   <span data-ttu-id="d8925-109">Могут создаваться новые приложения WF3, а существующие приложения можно изменить в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], при этом они полностью поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d8925-109">New WF3 applications can be created and your existing applications can be edited in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and are fully supported.</span></span>  
  
 <span data-ttu-id="d8925-110">Таким образом, решение об использовании .NET Framework 4 связано с решением о переходе на WF4 (System.Activities.*) с WF3 (System.Workflow.\*).</span><span class="sxs-lookup"><span data-stu-id="d8925-110">Thus, the decision to adopt the .NET Framework 4 is decoupled from your decision to move to WF4 (System.Activities.*) from WF3 (System.Workflow.\*).</span></span> <span data-ttu-id="d8925-111">В этом разделе приведены ссылки на руководство по миграции в WF, в котором описывается работа с WF3 и WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-111">This topic provides links to WF migration guidance that provides information about working with WF3 and WF4.</span></span>  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a><span data-ttu-id="d8925-112">Техническая документация и рецепты по миграции WF.</span><span class="sxs-lookup"><span data-stu-id="d8925-112">WF Migration Whitepapers and Cookbooks</span></span>  
 <span data-ttu-id="d8925-113">[Общие сведения о миграции WF](http://go.microsoft.com/fwlink/?LinkId=153873) разделе представлен подробный обзор связи между стратегиями миграции WF3 и WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-113">The [WF Migration Overview](http://go.microsoft.com/fwlink/?LinkId=153873) topic provides a broad overview of the relationship between WF3 and WF4 and migration strategies.</span></span> <span data-ttu-id="d8925-114">В сопутствующих разделах описываются следующие темы.</span><span class="sxs-lookup"><span data-stu-id="d8925-114">Companion topics drill into specific topics.</span></span>  
  
 [<span data-ttu-id="d8925-115">Общие сведения о миграции WF</span><span class="sxs-lookup"><span data-stu-id="d8925-115">WF Migration Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=153873)  
 <span data-ttu-id="d8925-116">Описывает связи между WF3 и WF4, а также новые возможности пользователей технологии рабочих процессов в .NET 4.</span><span class="sxs-lookup"><span data-stu-id="d8925-116">Describes the relationship between WF3 and WF4, and the choices you have as a user or a potential user of workflow technology in .NET 4.</span></span>  
  
 [<span data-ttu-id="d8925-117">Миграция WF: Рекомендации по разработке WF3</span><span class="sxs-lookup"><span data-stu-id="d8925-117">WF Migration: Best Practices for WF3 Development</span></span>](http://go.microsoft.com/fwlink/?LinkId=153852)  
 <span data-ttu-id="d8925-118">Описывается разработка артефактов WF3 с учетом возможностей упрощения миграции на WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-118">Discusses how to design WF3 artifacts so they can be more easily migrated to WF4.</span></span>  
  
 [<span data-ttu-id="d8925-119">Руководство по WF: правила</span><span class="sxs-lookup"><span data-stu-id="d8925-119">WF Guidance: Rules</span></span>](http://go.microsoft.com/fwlink/?LinkId=153854)  
 <span data-ttu-id="d8925-120">Описывает методы внедрения технологий, основанных на правилах, в решения [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8925-120">Discusses how to bring rules-related investments forward into [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] solutions.</span></span>  
  
 [<span data-ttu-id="d8925-121">Руководство по WF: Конечный автомат</span><span class="sxs-lookup"><span data-stu-id="d8925-121">WF Guidance: State Machine</span></span>](http://go.microsoft.com/fwlink/?LinkId=153855)  
 <span data-ttu-id="d8925-122">Описывает моделирование потока управления WF4 при отсутствии действия конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="d8925-122">Discusses WF4 control flow modeling in the absence of a State-Machine activity.</span></span>  
  
 <span data-ttu-id="d8925-123">Обратите внимание, что это руководство относится только к проектам рабочих процессов, использующих платформу .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d8925-123">Note that this guidance only applies to workflow projects that target .NET Framework 4.</span></span> <span data-ttu-id="d8925-124">Рабочие процессы конечного автомата были добавлены в .NET 4.0.1 с выпуском обновления платформы версии 1 и являлись частью платформы .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d8925-124">State Machine workflows were added in .NET 4.0.1 with the release of Platform Update 1, and were included as part of .NET Framework 4.5.</span></span> <span data-ttu-id="d8925-125">Дополнительные сведения о конечных автоматов в .NET 4.0.1 - 4.0.3 и .NET Framework 4.5 см. в разделе [обновление 4.0.1 компоненты Microsoft .NET Framework 4](http://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) и [конечных автоматов](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="d8925-125">For more information about state machine workflows in .NET 4.0.1 - 4.0.3 and .NET Framework 4.5, see [Update 4.0.1 for Microsoft .NET Framework 4 Features](http://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) and [State Machine Workflows](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).</span></span>  
  
 [<span data-ttu-id="d8925-126">Миграции WF: Настраиваемые действия</span><span class="sxs-lookup"><span data-stu-id="d8925-126">WF Migration Cookbook: Custom Activities</span></span>](http://go.microsoft.com/fwlink/?LinkId=153856)  
 <span data-ttu-id="d8925-127">Обеспечивает примеры и инструкции по изменению структуры настраиваемых действий WF3 в WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-127">Provides examples and instructions for redesigning WF3 custom activities on WF4.</span></span>  
  
 [<span data-ttu-id="d8925-128">Справочник по миграции WF: Расширенные настраиваемые действия</span><span class="sxs-lookup"><span data-stu-id="d8925-128">WF Migration Cookbook: Advanced Custom Activities</span></span>](http://go.microsoft.com/fwlink/?LinkId=275560)  
 <span data-ttu-id="d8925-129">Предоставляет рекомендации по перепроектированию расширенных пользовательских действий WF3, использующих очереди WF3 и планирование дочерних действий в виде пользовательских действий WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-129">Provides guidance for redesigning advanced WF3 custom activities that use WF3 queues and schedule child activities as WF4 custom activities.</span></span>  
  
 [<span data-ttu-id="d8925-130">Справочник по миграции WF: рабочие процессы</span><span class="sxs-lookup"><span data-stu-id="d8925-130">WF Migration Cookbook: Workflows</span></span>](http://go.microsoft.com/fwlink/?LinkId=153858)  
 <span data-ttu-id="d8925-131">Обеспечивает примеры и инструкции по изменению структуры рабочих процессов WF3 в WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-131">Provides examples and instructions for redesigning WF3 workflows on WF4.</span></span>  
  
 [<span data-ttu-id="d8925-132">Миграция WF: Размещение рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d8925-132">WF Migration Cookbook: Workflow Hosting</span></span>](http://go.microsoft.com/fwlink/?LinkId=275561)  
 <span data-ttu-id="d8925-133">Предоставляет рекомендации по перепроектированию кода размещения WF3 как кода размещения для WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-133">Provides guidance for redesigning WF3 hosting code as WF4 hosting code.</span></span> <span data-ttu-id="d8925-134">Цель - описать ключевые различия процессов размещения рабочего процесса в WF3 и WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-134">The goal is to cover the key differences in workflow hosting between WF3 and WF4.</span></span>  
  
 [<span data-ttu-id="d8925-135">Миграции WF: Отслеживание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d8925-135">WF Migration Cookbook: Workflow Tracking</span></span>](http://go.microsoft.com/fwlink/?LinkId=275562)  
 <span data-ttu-id="d8925-136">Предоставляет рекомендации по перепроектированию кода отслеживания и конфигурации WF3 при помощи эквивалентного кода отслеживания и конфигурации для WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-136">Provides guidance for redesigning WF3 tracking code and configuration using equivalent WF4 tracking code and configuration.</span></span>  
  
 [<span data-ttu-id="d8925-137">Руководство по WF: Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d8925-137">WF Guidance: Workflow Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=275564)  
 <span data-ttu-id="d8925-138">Предоставляет построенные на примерах пошаговые инструкции по перепроектированию часто используемых рабочих процессов, которые реализуют веб-службы Windows Communication Foundation (WCF) (называемые службами рабочих процессов), созданные в WF3, для использования средств WF4.</span><span class="sxs-lookup"><span data-stu-id="d8925-138">Provides example-oriented step-by-step instructions for redesigning workflows that implement Windows Communication Foundation (WCF) web services (commonly referred to as workflow services) created in WF3 to use WF4, for common scenarios for out-of-box activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8925-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d8925-139">See Also</span></span>  
 <xref:System.Activities.Statements.Interop>
