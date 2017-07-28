---
title: "Взаимодействие с политикой кэша: максимальный возраст и минимальная актуальность | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "политики кэша на основе времени"
  - "Политика "Повторная проверка""
  - "кэш [платформа .NET Framework], политики на основе времени"
  - "актуальность кэшированных ресурсов"
  - "политика в отношении максимального возраста"
  - "политика минимальной актуальности"
  - "возраст кэшированных ресурсов"
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Взаимодействие с политикой кэша: максимальный возраст и минимальная актуальность
Чтобы обеспечить самое свежее содержимое возвращаются клиентскому приложению, взаимодействие политики кэша клиента и требования к повторной проверки сервера всегда приводятся в наиболее консервативной политику кэша.  Все примеры в этом подразделе иллюстрируют политику кэширования для ресурса, кэшируемого истекает 1\-ого января. и 4\-ого января.  
  
 Следующие примеры иллюстрируют политики кэша, результаты из взаимодействия максимальную длительность \(`maxAge`\) и минимальных значений актуальности \(`minFresh`\).  
  
-   Если политика кэша устанавливает `maxAge` \= 2 дней и `minFresh` не указан, то содержимое revalidated 3\-его января.  
  
-   Если наборы `maxAge` политики кэша \= 2 дней и `minFresh` \= 1 день, в соответствии с `maxAge`, содержимое свежи до 3\-его января.  В соответствии с `minFresh`, содержимое свеже до 3\-его января.  Поэтому содержимое должно быть revalidated 3\-его января.  
  
-   Если наборы `maxAge`  политики кэша \= 2 дней и `minFresh` \= 2 дня, в соответствии с `maxAge`, содержимое свежи до 3\-его января.  В соответствии с `minFresh` содержимое свеже до 2\-ого января.  Поэтому содержимое должно быть revalidated 2\-ого января.  
  
## См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)   
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Настройка кэширования в сетевых приложениях](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [Взаимодействие с политикой кэша: максимальный возраст и устаревание](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)