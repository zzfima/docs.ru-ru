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
ms.openlocfilehash: 0a03438968f487f574606f415fb9d43223030038
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222159"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="32bff-102">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="32bff-102">Startup settings schema</span></span>

<span data-ttu-id="32bff-103">Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="32bff-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="32bff-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="32bff-104">Element</span></span>|<span data-ttu-id="32bff-105">Описание</span><span class="sxs-lookup"><span data-stu-id="32bff-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32bff-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="32bff-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="32bff-107">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="32bff-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="32bff-108">Приложения, созданные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="32bff-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="32bff-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="32bff-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="32bff-110">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="32bff-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="32bff-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="32bff-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="32bff-112">Содержит элементы **\<requiredRuntime>** и **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="32bff-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32bff-113">См. также</span><span class="sxs-lookup"><span data-stu-id="32bff-113">See also</span></span>

- [<span data-ttu-id="32bff-114">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="32bff-114">Configuration File Schema</span></span>](../index.md)  
- [<span data-ttu-id="32bff-115">Практическое руководство. Настройка приложения для поддержки .NET Framework 4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="32bff-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)