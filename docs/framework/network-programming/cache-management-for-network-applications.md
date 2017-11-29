---
title: "Управление кэшем для сетевых приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b960942d17e402b333354bbd932cf63d11b1209f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cache-management-for-network-applications"></a>Управление кэшем для сетевых приложений
В этом разделе и его подразделах описывается кэширование ресурсов, полученных с помощью классов <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> и <xref:System.Net.FtpWebRequest>.  
  
 Кэш обеспечивает временное хранение ресурсов, которые были запрошены приложением. Если приложение запрашивает один и тот же ресурс несколько раз, он может быть возвращен из кэша. Это позволяет избежать лишнего расходования ресурсов, связанного с его повторным запросом с сервера. Кэширование может повысить производительность приложения, ускоряя получение запрашиваемых ресурсов. Оно также может помочь уменьшить объем сетевого трафика, сокращая число обращений к серверу. Хотя кэширование повышает производительность, также растет риск того, что возвращаемый приложению ресурс может оказаться устаревшим, то есть отличающимся от того ресурса, который был бы отправлен с сервера при отсутствии кэширования.  
  
 Из-за кэширования также возможен несанкционированный доступ к конфиденциальным данным со стороны пользователей или процессов. Прошедший проверку подлинности ответ может быть получен из кэша без дополнительной авторизации. Если кэширование включено, измените значение <xref:System.Net.WebRequest.CachePolicy%2A> на <xref:System.Net.Cache.RequestCacheLevel.BypassCache> или <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore>, чтобы отключить кэширование для запроса.  
  
 По соображениям безопасности кэширование **не** рекомендуется использовать в сценариях среднего уровня.  
  
## <a name="in-this-section"></a>Содержание  
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)  
 Описывается, что такое политика кэша и как ее определить.  
  
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 Описание каждого типа политики кэша на основе расположения для ресурсов HTTP и HTTPS.  
  
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 Описание условий, которые можно использовать для настройки политики кэша на основе времени.  
  
 [Настройка кэширования в сетевых приложениях](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 Описываются программные способы создания политик кэша и запросов, для которых применяется кэширование.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Net.Cache>  
 Определение типов и перечислений, используемых для определения политик кэширования ресурсов, получаемых с помощью классов <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> и <xref:System.Net.FtpWebRequest>.
