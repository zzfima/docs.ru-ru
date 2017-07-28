---
title: "Проекции запросов (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "проекция [службы WCF Data Services]"
  - "проекция запроса [службы WCF Data Services]"
  - "Службы WCF Data Services, проекция"
  - "Службы WCF Data Services, запрос"
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Проекции запросов (службы WCF Data Services)
Проекция предоставляет службам [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] механизм для уменьшения объема данных в канале, возвращаемых запросом при указании, что в ответе возвращаются только определенные свойства сущности.  Дополнительные сведения см. в разделе [OData: параметр системного запроса выбора \($select\)](http://go.microsoft.com/fwlink/?LinkId=186076).  
  
 В этом разделе описано, как определить проекции запроса, какие требования предъявляются к типам сущности и несущностным типам, как выполнить обновления спроецированных результатов, создать проецируемые типы, а также представляются некоторые вопросы проекции.  
  
## Определение проекции запроса  
 Предложение проекции можно добавить в запрос, используя либо параметр запроса `$select` в URI, либо предложение [select](../Topic/select%20clause%20\(C%23%20Reference\).md) \([Select](../Topic/Select%20Clause%20\(Visual%20Basic\).md) в Visual Basic\) в запросе LINQ.  Возвращаемые данные сущности могут быть проецированы в типы сущностей или в типы, отличные от сущностей, на клиенте.  В примерах этого раздела показано, как использовать предложение `select` в запросе LINQ.  
  
> [!IMPORTANT]
>  При сохранении обновлений, выполненных в проецируемых типах, в службе данных может произойти потеря данных.  Дополнительные сведения см. в разделе [Вопросы проекции](#considerations).  
  
## Требования к типам сущностей и несущностным типам  
 Типы сущностей должны содержать одно или несколько свойств идентификатора, которые составляют ключ сущности.  Типы сущностей определяются на клиентах одним из следующих способов.  
  
-   Применением атрибута <xref:System.Data.Services.Common.DataServiceKeyAttribute> или <xref:System.Data.Services.Common.DataServiceEntityAttribute> к типу.  
  
-   Если тип имеет свойство, именуемое `ID`.  
  
-   Если тип имеет свойство, именуемое *type*`ID`, где *type* является именем типа.  
  
 По умолчанию, если результаты запроса проецируются на тип, определенный на клиенте, свойства, запрашиваемые в проекции, должны существовать в типе клиента.  Но если задается значение `true` для свойства <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> для <xref:System.Data.Services.Client.DataServiceContext>, не требуется, чтобы свойства, заданные в проекции, были в типе клиента.  
  
### Выполнение обновлений спроецированных результатов  
 При выполнении проекции результатов запроса на типы сущностей объект <xref:System.Data.Services.Client.DataServiceContext> может отслеживать объекты с обновлениями, которые должны передаваться вновь в службу данных, если вызывается метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  Однако обновления, выполненные в данных, проецируемых на клиенте на несущностные типы, не могут передаваться обратно в службу данных.  Это является следствием того, что без ключа для идентификации экземпляра сущности служба данных не может обновить правильную сущность в источнике данных.  Несущностные типы не прикрепляются к объекту <xref:System.Data.Services.Client.DataServiceContext>.  
  
 Если одно или несколько свойств типа сущности, определенного в службе данных, не проявляются в типе клиента, в который спроецирована сущность, вставки новых сущностей не будут содержать эти отсутствующие свойства.  В этом случае обновления, выполненные в существующих сущностях, **также** не будут включать эти отсутствующие свойства.  Если для такого свойства существует значение, обновление сбрасывает его в значение по умолчанию для свойства, как определено в источнике данных.  
  
### Создание проецируемых типов  
 В следующем примере используется анонимный запрос LINQ, который проецирует связанные с адресом свойства типа `Customers` в новый тип `CustomerAddress`, как определено на клиенте, и помечается как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressspecific)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressspecific)]  
  
 В этом примере шаблон инициализатора объекта используется для создания нового экземпляра типа `CustmerAddress` вместо вызова конструктора.  При проецировании в типы сущностей конструкторы не поддерживаются, но они могут использоваться при проецировании в несущностные типы и в анонимные типы.  Поскольку `CustomerAddress` имеет тип сущности, изменения могут быть сделаны и отправлены обратно в службу данных.  
  
 Кроме того, данные из типа `Customer` проецируются в экземпляр типа сущности `CustomerAddress`, а не в анонимный тип.  Проецирование в типы сущностей поддерживается, но данные доступны только для чтения, поскольку анонимные типы рассматриваются как несущностные типы.  
  
 Параметры <xref:System.Data.Services.Client.MergeOption> объекта <xref:System.Data.Services.Client.DataServiceContext> используются для разрешения идентификатора во время проекции запроса.  Это означает, что, если экземпляр типа `Customer` уже существует в объекте <xref:System.Data.Services.Client.DataServiceContext>, экземпляр `CustomerAddress` с тем же идентификатором будет следовать правилам разрешения идентификатора, установленным параметром <xref:System.Data.Services.Client.MergeOption>  
  
 В следующей таблице описаны особенности поведения при проецировании результатов в типы сущностей и в типы несущности.  
  
|Действие|Тип сущности|Несущностные типы|  
|--------------|------------------|-----------------------|  
|Создание нового спроецированного экземпляра с использованием инициализаторов, как в следующем примере:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithinitializer)]
 [!code-vb[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithinitializer)]|Поддерживается|Поддерживается|  
|Создание нового спроецированного экземпляра с использованием конструкторов, как в следующем примере:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithconstructor)]
 [!code-vb[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithconstructor)]|Вызывается исключение <xref:System.NotSupportedException>.|Поддерживается|  
|Использование проекции для преобразования значения свойства, как в следующем примере:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithtransform)]
 [!code-vb[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithtransform)]<br /><br /> Это преобразование не поддерживается для типов сущности, поскольку оно может вести к путанице, а также к возможной переписи данных в источнике данных, который относится к другой сущности.|Вызывается исключение <xref:System.NotSupportedException>.|Поддерживается|  
  
<a name="considerations"></a>   
## Вопросы проекции  
 При определении проекции запроса следует учитывать следующие дополнительные соображения.  
  
-   При определении пользовательских потоков для формата Atom следует убедиться, что все свойства сущностей, имеющие пользовательские сопоставления, включены в проекцию.  Если сопоставленное свойство сущности не включено в проекцию, может произойти потеря данных.  Для получения дополнительной информации см. [Настройка канала](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
-   Если вставки выполняются в проецированный тип, который не содержит все свойства сущности в модели данных службы данных, свойства, не включенные в проекцию на клиенте, устанавливаются в их значения по умолчанию.  
  
-   Если обновления выполняются в проецированном типе, который не содержит все свойства сущности в модели данных службы данных, существующие значения, не включенные в проекцию на клиенте, будут переписаны инициализированными значениями по умолчанию.  
  
-   Если проекция включает сложное свойство, должен быть возвращен весь сложный объект.  
  
-   Если проекция включает свойство навигации, связанные объекты загружаются неявно, без вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>.  Метод <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> не поддерживается для использования в проецированном запросе.  
  
-   Запросы проецирования запроса на клиенте преобразуются для использования параметра запроса `$select` в URI запроса.  Если выполняется запрос с проекцией по отношению к предыдущей версии [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], которая не поддерживает параметр запроса `$select`, то возвращается ошибка. Это также может произойти, если версия <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> поведения <xref:System.Data.Services.DataServiceBehavior> для службы данных задается равной значению <xref:System.Data.Services.Common.DataServiceProtocolVersion>.  Для получения дополнительной информации см. [Управление версиями данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
 Для получения дополнительной информации см. [Как проецировать результаты запроса](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).  
  
## См. также  
 [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)