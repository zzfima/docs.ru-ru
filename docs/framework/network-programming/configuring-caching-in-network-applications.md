---
title: "Настройка кэширования в сетевых приложениях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cache [.NET Framework], configuring
ms.assetid: 3f694a1c-de5d-47cf-a6eb-cfc369fb8a9f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3c06c05f2d5102d1822aa11c81f2814090e10ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-caching-in-network-applications"></a><span data-ttu-id="9b436-102">Настройка кэширования в сетевых приложениях</span><span class="sxs-lookup"><span data-stu-id="9b436-102">Configuring Caching in Network Applications</span></span>
<span data-ttu-id="9b436-103">Чтобы настроить кэширование, необходимо указать политику кэширования на уровне приложения или <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="9b436-103">To configure caching, you must specify a cache policy at the application or <xref:System.Net.WebRequest> level.</span></span> <span data-ttu-id="9b436-104">В следующих разделах приводятся примеры кода, которые демонстрируют настройку приложений и запросов для использования кэширования.</span><span class="sxs-lookup"><span data-stu-id="9b436-104">The following topics provide code examples that demonstrate configuring applications and requests to use caching.</span></span>  
  
-   [<span data-ttu-id="9b436-105">Практическое руководство. Установка политики кэша для приложения на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9b436-105">How to: Set a Location-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="9b436-106">Практическое руководство. Установка политики кэша для приложения на основе времени по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9b436-106">How to: Set the Default Time-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="9b436-107">Практическое руководство. Настройка политики кэша на основе времени</span><span class="sxs-lookup"><span data-stu-id="9b436-107">How to: Customize a Time-Based Cache Policy</span></span>](../../../docs/framework/network-programming/how-to-customize-a-time-based-cache-policy.md)  
  
-   [<span data-ttu-id="9b436-108">Практическое руководство. Задание политики кэширования для запроса</span><span class="sxs-lookup"><span data-stu-id="9b436-108">How to: Set Cache Policy for a Request</span></span>](../../../docs/framework/network-programming/how-to-set-cache-policy-for-a-request.md)  
  
 <span data-ttu-id="9b436-109">Также для настройки политики кэширования можно использовать файлы конфигурации приложения или компьютера.</span><span class="sxs-lookup"><span data-stu-id="9b436-109">You can also configure cache policy using application or machine configuration files.</span></span> <span data-ttu-id="9b436-110">Дополнительные сведения см. в разделе [Элемент \<requestCaching> (сетевые параметры)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9b436-110">For more information, see &#124; [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b436-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9b436-111">See Also</span></span>  
 [<span data-ttu-id="9b436-112">Управление кэшем для сетевых приложений</span><span class="sxs-lookup"><span data-stu-id="9b436-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="9b436-113">Политика кэша</span><span class="sxs-lookup"><span data-stu-id="9b436-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="9b436-114">Политики кэша на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9b436-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="9b436-115">Политики кэша на основе времени</span><span class="sxs-lookup"><span data-stu-id="9b436-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
