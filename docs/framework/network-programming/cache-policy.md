---
title: Cache Policy
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
ms.openlocfilehash: 2d3d85ebd80f417ebd0fa0e619097e15f2a6a39b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048775"
---
# <a name="cache-policy"></a>Cache Policy
Политика кэша определяет правила, согласно которым определяется возможность выполнения запроса с помощью кэшированной копии запрашиваемого ресурса. В приложениях указываются требования к кэшу клиента в плане актуальности, однако фактическая политика кэша определяется требованиями к кэшу клиента, требованиями сервера к сроку действия и требованиями сервера к повторной проверке. Чтобы обеспечить возврат клиентскому приложению самого актуального содержимого, в результате взаимодействия политики кэша клиента и требований сервера всегда применяется наиболее консервативная политика кэша.  
  
 Политики кэша могут быть основаны на расположении или времени. Политика кэша на основе расположения определяет актуальность записей в кэше на основе расположения, из которого может быть получен запрашиваемый ресурс. Политика кэша на основе времени определяет актуальность записей в кэше на основе времени извлечения ресурса, заголовков, возвращаемых вместе с ним, и текущего времени. Большинство приложений могут использовать политику кэширования по умолчанию на основе времени, которая реализует спецификацию RFC 2616, доступную на веб-сайте [Internet Engineering Task Force (IETF)](https://www.ietf.org/).  
  
 В приведенной ниже таблице описываются классы, используемые для настройки политик кэширования.  
  
|Имя класса|Описание:|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Представляет политики кэша на основе расположения и на основе времени для ресурсов, запрашиваемых с помощью объектов <xref:System.Net.HttpWebRequest>.|  
|<xref:System.Net.Cache.RequestCachePolicy>|Представляет политики кэша на основе расположения или политики кэша на основе времени <xref:System.Net.Cache.RequestCacheLevel.Default> для ресурсов, запрашиваемых с помощью объектов <xref:System.Net.WebRequest>.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Задает значения, используемые для создания объектов <xref:System.Net.Cache.HttpRequestCachePolicy> на основе времени.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Задает значения, используемые для создания объектов <xref:System.Net.Cache.HttpRequestCachePolicy> на основе расположения и на основе времени.|  
|<xref:System.Net.Cache.RequestCacheLevel>|Задает значения, используемые для создания объектов <xref:System.Net.Cache.RequestCacheLevel.Default> на основе расположения или на основе времени <xref:System.Net.Cache.RequestCachePolicy>.|  
  
 Определить политику кэша можно для всех запросов, совершаемых приложением, или для отдельных запросов. Если определены политики кэша как на уровне приложения, так и на уровне запросов, применяется политика на уровне запросов. Политику кэша на уровне приложения можно настроить программными средствами либо с помощью файлов конфигурации приложения или компьютера. Дополнительные сведения см. в разделе [Элемент \<requestCaching> (сетевые параметры)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Чтобы создать политику кэша, необходимо создать объект политики как экземпляр класса <xref:System.Net.Cache.RequestCachePolicy> или <xref:System.Net.Cache.HttpRequestCachePolicy>. Чтобы задать политику для запроса, присвойте объект политики свойству <xref:System.Net.WebRequest.CachePolicy%2A> запроса. Если вы настраиваете политику на уровне приложения программными средствами, присвойте объект политики свойству <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A>.  
  
 Примеры кода, демонстрирующие создание и использование политик кэша, см. в разделе [Настройка кэширования в сетевых приложениях](configuring-caching-in-network-applications.md).  
  
## <a name="see-also"></a>См. также раздел

- [Управление кэшем для сетевых приложений](cache-management-for-network-applications.md)
- [Политики кэша на основе расположения](location-based-cache-policies.md)
- [Политики кэша на основе времени](time-based-cache-policies.md)
- [Настройка кэширования в сетевых приложениях](configuring-caching-in-network-applications.md)
