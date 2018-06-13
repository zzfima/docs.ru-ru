---
title: Схема параметров запуска
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59f0441b79244eb529be338495c32af886a5f2b3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745101"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="6eae1-102">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="6eae1-102">Startup Settings Schema</span></span>
<span data-ttu-id="6eae1-103">Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="6eae1-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="6eae1-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="6eae1-104">Element</span></span>|<span data-ttu-id="6eae1-105">Описание</span><span class="sxs-lookup"><span data-stu-id="6eae1-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6eae1-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="6eae1-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="6eae1-107">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6eae1-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="6eae1-108">Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="6eae1-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="6eae1-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="6eae1-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="6eae1-110">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="6eae1-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="6eae1-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="6eae1-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="6eae1-112">Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="6eae1-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6eae1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6eae1-113">See Also</span></span>  
 [<span data-ttu-id="6eae1-114">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6eae1-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6eae1-115">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6eae1-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
