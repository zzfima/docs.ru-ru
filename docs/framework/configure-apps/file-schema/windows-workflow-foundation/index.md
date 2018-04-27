---
title: Схема конфигурации Windows Workflow Foundation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7ae70357-b150-4342-8f2a-d5eb6f9c6a0d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9644b1e25c8d1568a01434a587e4271b163a3f0b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="windows-workflow-foundation-configuration-schema"></a><span data-ttu-id="15494-102">Схема конфигурации Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="15494-102">Windows Workflow Foundation Configuration Schema</span></span>
<span data-ttu-id="15494-103">Элементы конфигурации Windows Workflow Foundation (WF) позволяют настроить приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="15494-103">Windows Workflow Foundation (WF) configuration elements enable you to configure workflow applications.</span></span> <span data-ttu-id="15494-104">Помимо прочего, для приложения рабочего процесса можно настроить отслеживание и трассировку.</span><span class="sxs-lookup"><span data-stu-id="15494-104">For a workflow application, you can configure among other things, tracking and tracing.</span></span> <span data-ttu-id="15494-105">Дополнительные сведения о трассировке и отслеживании см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="15494-105">For more information about tracking and tracing, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="15494-106">Для служб рабочего процесса можно также настроить элементы конфигурации [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15494-106">For workflow services, you can also use [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] configuration elements.</span></span> <span data-ttu-id="15494-107">Дополнительные сведения о [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] см. в разделе [Схема конфигурации WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="15494-107">For more details about [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], see [WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="15494-108">Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом.</span><span class="sxs-lookup"><span data-stu-id="15494-108">Because configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="15494-109">В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="15494-109">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="15494-110">Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="15494-110">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15494-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="15494-111">In This Section</span></span>  
 [<span data-ttu-id="15494-112">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="15494-112">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/system-servicemodel-of-workflow.md)  
 <span data-ttu-id="15494-113">Описывается элемент **ServiceModel**.</span><span class="sxs-lookup"><span data-stu-id="15494-113">Describes the **ServiceModel** element.</span></span>
