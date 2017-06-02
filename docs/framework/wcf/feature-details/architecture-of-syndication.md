---
title: "Архитектура синдикации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed4ca86e-e3d8-4acb-87aa-1921fbc353be
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Архитектура синдикации
API синдикации предназначен для обеспечения независимой от формата модели программирования, которая позволяет передавать сводное содержимое по каналам связи в различных форматах.  Абстрактная модель данных состоит из следующих классов:  
  
-   <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 Эти классы тесно сопоставлены с конструкциями, определенными в спецификации Atom 1.0, хотя некоторые имена различаются.  
  
 В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] веб\-каналы синдикации моделируются в виде операции службы другого типа, у которого возвращаемым типом является один из производных классов для класса <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.  Извлечение веб\-канала моделируется в виде обмена сообщениями «запрос\-ответ».  Клиент отправляет службе запрос, а служба отвечает.  Сообщение с запросом задается протоколом инфраструктуры \(например, чистым HTTP\), а сообщение ответа содержит полезные данные в общепринятом формате синдикации \(RSS 2.0 или Atom 1.0\).  Службы, реализующие подобные механизмы обмена сообщениями, называются службами синдикации.  
  
 Контракт службы синдикации состоит из набора операций, которые возвращают экземпляр класса <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.  В следующем примере показано объявление интерфейса для службы синдикации.  
  
 [!code-csharp[S_UE_SyndicationBoth#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_syndicationboth/cs/service.cs#0)]  
  
 Поддержка синдикации осуществляется на базе модели программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST, которая определяет привязку <xref:System.ServiceModel.WebHttpBinding>, используемую совместно с поведением <xref:System.ServiceModel.Description.WebHttpBehavior>, которая предоставляет доступ к каналам в виде служб.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] REST модели программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Общие сведения о модели программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md).  
  
> [!NOTE]
>  Спецификация Atom 1.0 позволяет указывать точность выборки в долях секунды во всех структурах даты.  При сериализации и десериализации в реализации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] доли секунды игнорируются.  
  
## Объектная модель  
 Объектная модель синдикации состоит из групп классов в следующих таблицах.  
  
 Классы форматирования:  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter>|Класс, который выполняет сериализацию экземпляра <xref:System.ServiceModel.Syndication.SyndicationFeed> в формат Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601>|Класс, который выполняет сериализацию классов, производных от <xref:System.ServiceModel.Syndication.SyndicationFeed>, в формат Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter>|Класс, который выполняет сериализацию экземпляра <xref:System.ServiceModel.Syndication.SyndicationItem> в формат Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601>|Класс, который выполняет сериализацию классов, производных от <xref:System.ServiceModel.Syndication.SyndicationItem>, в формат Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter>|Класс, который выполняет сериализацию экземпляра <xref:System.ServiceModel.Syndication.SyndicationFeed> в формат RSS 2.0.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>|Класс, который выполняет сериализацию классов, производных от <xref:System.ServiceModel.Syndication.SyndicationFeed>, в формат RSS 2.0.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter>|Класс, который выполняет сериализацию экземпляра <xref:System.ServiceModel.Syndication.SyndicationItem> в формат RSS 2.0.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>|Класс, который выполняет сериализацию классов, производных от <xref:System.ServiceModel.Syndication.SyndicationItem>, в формат RSS 2.0.|  
  
 Классы объектной модели  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.ServiceModel.Syndication.SyndicationCategory>|Класс, представляющий категорию веб\-канала синдикации.|  
|<xref:System.ServiceModel.Syndication.SyndicationContent>|Базовый класс, представляющий содержимое синдикации.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtension>|Класс, представляющий расширение элемента синдикации.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection>|Коллекция объектов <xref:System.ServiceModel.Syndication.SyndicationElementExtension>.|  
|<xref:System.ServiceModel.Syndication.SyndicationFeed>|Класс, представляющий объект веб\-канала верхнего уровня.|  
|<xref:System.ServiceModel.Syndication.SyndicationItem>|Класс, представляющий элемент веб\-канала.|  
|<xref:System.ServiceModel.Syndication.SyndicationLink>|Класс, представляющий ссылку в веб\-канале или элементе синдикации.|  
|<xref:System.ServiceModel.Syndication.SyndicationPerson>|Класс, представляющий конструкцию Person спецификации Atom.|  
|<xref:System.ServiceModel.Syndication.SyndicationVersions>|Класс, представляющий поддерживаемые версии протоколов синдикации.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContent>|Класс, представляющий любое содержимое <xref:System.ServiceModel.Syndication.SyndicationItem>, которое требуется отобразить для конечного пользователя.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContentKind>|Перечисление, представляющее различные типы поддерживаемого текстового содержимого синдикации.|  
|<xref:System.ServiceModel.Syndication.UrlSyndicationContent>|Класс, представляющий содержимое синдикации, которое содержит URL\-адрес другого ресурса.|  
|<xref:System.ServiceModel.Syndication.XmlSyndicationContent>|Класс, представляющий содержимое синдикации, которое не подлежит отображению в браузере.|  
  
 Базовыми абстракциями данных в объектной модели являются веб\-канал и элемент, которые соответствуют классам <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>.  Веб\-канал предоставляет метаданные соответствующего уровня \(например, заголовок, описание и имя автора\), расположение для хранения неизвестных расширений, а также набор элементов, из которых состоит остальное содержимое веб\-канала.  Элемент предоставляет метаданные соответствующего уровня \(например, заголовок, краткое описание и дату публикации\), расположение для хранения неизвестных расширений, а также блок содержимого, включающий остальное содержимое элемента.  Базовые абстракции потока и элемента поддерживаются дополнительными классами, которые представляют общие структуры данных, описанные в спецификациях Atom 1.0 и RSS.  
  
 Сведения, хранящиеся в экземпляре веб\-канала, можно преобразовать в различные форматы XML.  Процесс преобразования в формат XML и обратно управляется классом <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.  Это абстрактный класс; конкретные реализации для спецификаций Atom 1.0 и RSS 2.0 определяются классами <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> и <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>.  Для использования производных классов веб\-канала следует использовать <xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601> или <xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>, поскольку они позволяют задавать производный класс веб\-канала.  Для использования производных классов элемента следует использовать <xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601> или <xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>, поскольку они позволяют задавать производный класс элемента. Возможно также создание собственных производных реализаций класса <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>, поддерживающих другие форматы синдикации.  
  
## Расширение среды  
  
-   Ключевой особенностью протоколов синдикации является их расширяемость.  Оба протокола, Atom 1.0 и RSS 2.0, позволяют добавлять в веб\-каналы атрибуты и элементы, не определенные в спецификациях.  Модель программирования синдикации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает два способа работы с пользовательскими атрибутами и расширениями: создание производных классов и использования слабо типизированного доступа.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Расширяемость синдикации](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md).  
  
## См. также  
 [Общие сведения о синдикации WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)   
 [Сопоставление объектной модели синдикации WCF моделям Atom и RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)   
 [Модель веб\-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)