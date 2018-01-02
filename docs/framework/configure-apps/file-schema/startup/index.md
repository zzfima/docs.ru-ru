---
title: "Схема параметров запуска"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0536197d4cb8b30d99f514d8066e94bf84bffdf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="startup-settings-schema"></a><span data-ttu-id="cba5c-102">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="cba5c-102">Startup Settings Schema</span></span>
<span data-ttu-id="cba5c-103">Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="cba5c-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="cba5c-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="cba5c-104">Element</span></span>|<span data-ttu-id="cba5c-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="cba5c-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cba5c-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="cba5c-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="cba5c-107">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cba5c-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="cba5c-108">Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="cba5c-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="cba5c-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="cba5c-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="cba5c-110">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="cba5c-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="cba5c-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="cba5c-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="cba5c-112">Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="cba5c-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cba5c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cba5c-113">See Also</span></span>  
 [<span data-ttu-id="cba5c-114">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="cba5c-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="cba5c-115">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="cba5c-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
