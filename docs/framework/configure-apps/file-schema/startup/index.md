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
ms.openlocfilehash: 68f37e3efca784b94be90d5779c9bc402f144448
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465477"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="581af-102">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="581af-102">Startup Settings Schema</span></span>
<span data-ttu-id="581af-103">Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="581af-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="581af-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="581af-104">Element</span></span>|<span data-ttu-id="581af-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="581af-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="581af-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="581af-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="581af-107">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="581af-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="581af-108">Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="581af-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="581af-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="581af-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="581af-110">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="581af-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="581af-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="581af-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="581af-112">Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="581af-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="581af-113">См. также</span><span class="sxs-lookup"><span data-stu-id="581af-113">See Also</span></span>  
 [<span data-ttu-id="581af-114">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="581af-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="581af-115">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="581af-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
