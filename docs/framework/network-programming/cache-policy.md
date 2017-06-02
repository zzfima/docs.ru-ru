---
title: "Политика кэша | Microsoft Docs"
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
  - "политики кэша на основе расположения"
  - "кэш [платформа .NET Framework], политики"
  - "политики кэширования запроса"
  - "актуальность кэшированных ресурсов"
  - "политики кэширования содержимого"
  - "содержимое с истекшим сроком"
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Политика кэша
Политика кэша устанавливает правила, по которым определяется, можно ли удовлетворить тот или иной запрос с использованием кэшированной копии запрошенного ресурса.  Приложения задают требования к кэша клиента для актуальности, но эффективную политику кэша определяется требованиями к кэша клиента требованиями к срока действия сервера содержимым и требованиями к повторной проверки сервера.  Взаимодействие требований политики кэша клиента и сервера всегда приводит к наиболее консервативной политику кэша, чтобы обеспечить самое свежее содержимое возвращаемые клиентскому приложению.  
  
 Место хранения\- основаны или Time\- основаны политики кэша.  Место хранения\- на основе политики кэша, указывающее свежесть кэшированных записей на основе где запрошенный ресурс может браться из.  Time\- на основе политики кэша, указывающее свежесть кэшированных записей с помощью времени ресурс был получать заголовки, возвращенные с ресурсом, а текущее время.  Большинство приложений могут использовать Time\- based значение по умолчанию политики кэша, которая реализует политику кэширования, указанную в RFC 2616, [http:\/\/www.ietf.org](http://www.ietf.org/) доступном по адресу.  
  
 Классы, описанные в следующей таблице используются для задания политики кэша.  
  
|Имя класса|Описание|  
|----------------|--------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Представляет расположение хранения\- и Time\- на основе на основе политики кэша для ресурсов спрошенных с помощью объектов <xref:System.Net.HttpWebRequest>.|  
|<xref:System.Net.Cache.RequestCachePolicy>|Представляет расположение хранения\- на основе политики кэша или Time\- <xref:System.Net.Cache.RequestCacheLevel> на основе политики кэша для ресурсов спрошенных с помощью объектов <xref:System.Net.WebRequest>.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Определяет значения, используемые для создания Time\- на основе объектов <xref:System.Net.Cache.HttpRequestCachePolicy>.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Определяет значения, используемые для создания место хранения\- и Time\- объекты, основанные на основе <xref:System.Net.Cache.HttpRequestCachePolicy>.|  
|<xref:System.Net.Cache.RequestCacheLevel>|Определяет значения, используемые для создания место хранения\- или Time\- <xref:System.Net.Cache.RequestCacheLevel> объекты, основанные на <xref:System.Net.Cache.RequestCachePolicy>.|  
  
 Можно задать политику кэширования для всех запросов, выполняемых приложением или для отдельных запросов.  При указании и политику кэша уровня приложения и кэширует запрос\- уровень политики, запрос\- уровня политики.  Можно указать политику кэширования на уровне приложения программным образом или с помощью файлов конфигурации приложения или подвергнуть механической обработке.  Дополнительные сведения см. в разделе [Элемент \<requestCaching\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Создание политики кэша, необходимо создать объект политики путем создания экземпляра класса <xref:System.Net.Cache.RequestCachePolicy> или <xref:System.Net.Cache.HttpRequestCachePolicy>.  Для определения политики в запросе, установите свойство <xref:System.Net.WebRequest.CachePolicy%2A> запроса для объекта политики.  При установлении политики уровня приложения программным способом установите свойство <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> для объекта политики.  
  
 Примеры кода, демонстрирующие создание и использование политики кэша см. в разделе [Настройка кэширования в приложениях сети](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Настройка кэширования в сетевых приложениях](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)