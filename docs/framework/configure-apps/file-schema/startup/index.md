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
ms.openlocfilehash: 12f91a1c74e85cbce0c8f641f202a181beb7412c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728912"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="2a074-102">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="2a074-102">Startup settings schema</span></span>

<span data-ttu-id="2a074-103">Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="2a074-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="2a074-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a074-104">Element</span></span>|<span data-ttu-id="2a074-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a074-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a074-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="2a074-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="2a074-107">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2a074-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="2a074-108">Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="2a074-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="2a074-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="2a074-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="2a074-110">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="2a074-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="2a074-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="2a074-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="2a074-112">Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="2a074-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a074-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2a074-113">See also</span></span>

- [<span data-ttu-id="2a074-114">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="2a074-114">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2a074-115">Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше</span><span class="sxs-lookup"><span data-stu-id="2a074-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
