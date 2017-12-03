---
title: "Проекции запросов (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d14c67daa387f06a3c7d6e43219991950bceb73e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="query-projections-wcf-data-services"></a>Проекции запросов (службы данных WCF)
Проекция представляет собой механизм в [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для уменьшения объема данных в веб-канале, возвращаемые запросом, указав в ответе возвращаются только определенные свойства сущности. Дополнительные сведения см. в разделе [OData: параметр системного запроса ($select)](http://go.microsoft.com/fwlink/?LinkId=186076).  
  
 В этом разделе описано, как определить проекции запроса, какие требования предъявляются к типам сущности и несущностным типам, как выполнить обновления спроецированных результатов, создать проецируемые типы, а также представляются некоторые вопросы проекции.  
  
## <a name="defining-a-query-projection"></a>Определение проекции запроса  
 Можно добавить предложение проекции для запроса с помощью `$select` параметра в URI, либо с помощью запроса [выберите](~/docs/csharp/language-reference/keywords/select-clause.md) предложение ([выберите](~/docs/visual-basic/language-reference/queries/select-clause.md) в Visual Basic) в запросе LINQ. Возвращаемые данные сущности могут быть проецированы в типы сущностей или в типы, отличные от сущностей, на клиенте. В примерах этого раздела показано, как использовать предложение `select` в запросе LINQ.  
  
> [!IMPORTANT]
>  При сохранении обновлений, выполненных в проецируемых типах, в службе данных может произойти потеря данных. Дополнительные сведения см. в разделе [вопросы проекции](#considerations).  
  
## <a name="requirements-for-entity-and-non-entity-types"></a>Требования к типам сущностей и несущностным типам  
 Типы сущностей должны содержать одно или несколько свойств идентификатора, которые составляют ключ сущности. Типы сущностей определяются на клиентах одним из следующих способов.  
  
-   Применением атрибута <xref:System.Data.Services.Common.DataServiceKeyAttribute> или <xref:System.Data.Services.Common.DataServiceEntityAttribute> к типу.  
  
-   Если тип имеет свойство, именуемое `ID`.  
  
-   Если тип имеет свойство с именем *тип*`ID`, где *типа* является именем типа.  
  
 По умолчанию, если результаты запроса проецируются на тип, определенный на клиенте, свойства, запрашиваемые в проекции, должны существовать в типе клиента. Но если задается значение `true` для свойства <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> для <xref:System.Data.Services.Client.DataServiceContext>, не требуется, чтобы свойства, заданные в проекции, были в типе клиента.  
  
### <a name="making-updates-to-projected-results"></a>Выполнение обновлений спроецированных результатов  
 При выполнении проекции результатов запроса на типы сущностей объект <xref:System.Data.Services.Client.DataServiceContext> может отслеживать объекты с обновлениями, которые должны передаваться вновь в службу данных, если вызывается метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>. Однако обновления, выполненные в данных, проецируемых на клиенте на несущностные типы, не могут передаваться обратно в службу данных. Это является следствием того, что без ключа для идентификации экземпляра сущности служба данных не может обновить правильную сущность в источнике данных. Несущностные типы не прикрепляются к объекту <xref:System.Data.Services.Client.DataServiceContext>.  
  
 Если одно или несколько свойств типа сущности, определенного в службе данных, не проявляются в типе клиента, в который спроецирована сущность, вставки новых сущностей не будут содержать эти отсутствующие свойства. В этом случае будет обновления, выполненные в существующих сущностях **также** не включать эти отсутствующие свойства. Если для такого свойства существует значение, обновление сбрасывает его в значение по умолчанию для свойства, как определено в источнике данных.  
  
### <a name="creating-projected-types"></a>Создание проецируемых типов  
 В следующем примере используется анонимный запрос LINQ, который проецирует связанные с адресом свойства типа `Customers` в новый тип `CustomerAddress`, как определено на клиенте, и помечается как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressspecific)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressspecific)]  
  
 В этом примере шаблон инициализатора объекта используется для создания нового экземпляра типа `CustmerAddress` вместо вызова конструктора. При проецировании в типы сущностей конструкторы не поддерживаются, но они могут использоваться при проецировании в несущностные типы и в анонимные типы. Поскольку `CustomerAddress` имеет тип сущности, изменения могут быть сделаны и отправлены обратно в службу данных.  
  
 Кроме того, данные из типа `Customer` проецируются в экземпляр типа сущности `CustomerAddress`, а не в анонимный тип. Проецирование в типы сущностей поддерживается, но данные доступны только для чтения, поскольку анонимные типы рассматриваются как несущностные типы.  
  
 Параметры <xref:System.Data.Services.Client.MergeOption> объекта <xref:System.Data.Services.Client.DataServiceContext> используются для разрешения идентификатора во время проекции запроса. Это означает, что, если экземпляр типа `Customer` уже существует в объекте <xref:System.Data.Services.Client.DataServiceContext>, экземпляр `CustomerAddress` с тем же идентификатором будет следовать правилам разрешения идентификатора, установленным параметром <xref:System.Data.Services.Client.MergeOption>  
  
 В следующей таблице описаны особенности поведения при проецировании результатов в типы сущностей и в типы несущности.  
  
|Действие|Тип сущности|Несущностные типы|  
|------------|-----------------|----------------------|  
|Создание нового спроецированного экземпляра с использованием инициализаторов, как в следующем примере:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithinitializer)]
 [!code-vb[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithinitializer)]|Поддерживается|Поддерживается|  
|Создание нового спроецированного экземпляра с использованием конструкторов, как в следующем примере:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithconstructor)]
 [!code-vb[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithconstructor)]|Вызывается исключение <xref:System.NotSupportedException>.|Поддерживается|  
|Использование проекции для преобразования значения свойства, как в следующем примере:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithtransform)]
 [!code-vb[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithtransform)]<br /><br /> Это преобразование не поддерживается для типов сущности, поскольку оно может вести к путанице, а также к возможной переписи данных в источнике данных, который относится к другой сущности.|Вызывается исключение <xref:System.NotSupportedException>.|Поддерживается|  
  
<a name="considerations"></a>   
## <a name="projection-considerations"></a>Вопросы проекции  
 При определении проекции запроса следует учитывать следующие дополнительные соображения.  
  
-   При определении пользовательских потоков для формата Atom следует убедиться, что все свойства сущностей, имеющие пользовательские сопоставления, включены в проекцию. Если сопоставленное свойство сущности не включено в проекцию, может произойти потеря данных. Дополнительные сведения см. в разделе [настройки веб-канал](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
-   Если вставки выполняются в проецированный тип, который не содержит все свойства сущности в модели данных службы данных, свойства, не включенные в проекцию на клиенте, устанавливаются в их значения по умолчанию.  
  
-   Если обновления выполняются в проецированном типе, который не содержит все свойства сущности в модели данных службы данных, существующие значения, не включенные в проекцию на клиенте, будут переписаны инициализированными значениями по умолчанию.  
  
-   Если проекция включает сложное свойство, должен быть возвращен весь сложный объект.  
  
-   Если проекция включает свойство навигации, связанные объекты загружаются неявно, без вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>. Метод <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> не поддерживается для использования в проецированном запросе.  
  
-   Запросы проецирования запроса на клиенте преобразуются для использования параметра запроса `$select` в URI запроса. Если запрос с проекцией выполняется для предыдущей версии служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], которая не поддерживает параметр запроса `$select`, возвращается ошибка. Это может также произойти, если версия <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> объекта <xref:System.Data.Services.DataServiceBehavior> для службы данных установлена в значение <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1>. Дополнительные сведения см. в разделе [управление версиями службы данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
 Дополнительные сведения см. в разделе [как: результаты запроса проекта](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
