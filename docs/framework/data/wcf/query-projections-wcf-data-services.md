---
title: Проекции запросов (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
ms.openlocfilehash: d53892f9823474ea14640e352548b55432e7744b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461067"
---
# <a name="query-projections-wcf-data-services"></a>Проекции запросов (службы данных WCF)
Проекция предоставляет механизм в [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для уменьшения объема данных в веб-канале, возвращаемых запросом, указав, что в ответе возвращаются только определенные свойства сущности. Дополнительные сведения см. в разделе [OData: параметр системного запроса выбора ($select)](https://go.microsoft.com/fwlink/?LinkId=186076).  
  
 В этом разделе описано, как определить проекции запроса, какие требования предъявляются к типам сущности и несущностным типам, как выполнить обновления спроецированных результатов, создать проецируемые типы, а также представляются некоторые вопросы проекции.  
  
## <a name="defining-a-query-projection"></a>Определение проекции запроса  
 Можно добавить предложение проекции к запросу с помощью `$select` параметр в URI, либо с помощью запроса [выберите](~/docs/csharp/language-reference/keywords/select-clause.md) предложение ([выберите](~/docs/visual-basic/language-reference/queries/select-clause.md) в Visual Basic) в запросе LINQ. Возвращаемые данные сущности могут быть проецированы в типы сущностей или в типы, отличные от сущностей, на клиенте. В примерах этого раздела показано, как использовать предложение `select` в запросе LINQ.  
  
> [!IMPORTANT]
>  При сохранении обновлений, выполненных в проецируемых типах, в службе данных может произойти потеря данных. Дополнительные сведения см. в разделе [вопросы проекции](#considerations).  
  
## <a name="requirements-for-entity-and-non-entity-types"></a>Требования к типам сущностей и несущностным типам  
 Типы сущностей должны содержать одно или несколько свойств идентификатора, которые составляют ключ сущности. Типы сущностей определяются на клиентах одним из следующих способов.  
  
-   Применением атрибута <xref:System.Data.Services.Common.DataServiceKeyAttribute> или <xref:System.Data.Services.Common.DataServiceEntityAttribute> к типу.  
  
-   Если тип имеет свойство, именуемое `ID`.  
  
-   Если тип имеет свойство с именем *тип*`ID`, где *тип* имя типа.  
  
 По умолчанию, если результаты запроса проецируются на тип, определенный на клиенте, свойства, запрашиваемые в проекции, должны существовать в типе клиента. Но если задается значение `true` для свойства <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> для <xref:System.Data.Services.Client.DataServiceContext>, не требуется, чтобы свойства, заданные в проекции, были в типе клиента.  
  
### <a name="making-updates-to-projected-results"></a>Выполнение обновлений спроецированных результатов  
 При выполнении проекции результатов запроса на типы сущностей объект <xref:System.Data.Services.Client.DataServiceContext> может отслеживать объекты с обновлениями, которые должны передаваться вновь в службу данных, если вызывается метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>. Однако обновления, выполненные в данных, проецируемых на клиенте на несущностные типы, не могут передаваться обратно в службу данных. Это является следствием того, что без ключа для идентификации экземпляра сущности служба данных не может обновить правильную сущность в источнике данных. Несущностные типы не прикрепляются к объекту <xref:System.Data.Services.Client.DataServiceContext>.  
  
 Если одно или несколько свойств типа сущности, определенного в службе данных, не проявляются в типе клиента, в который спроецирована сущность, вставки новых сущностей не будут содержать эти отсутствующие свойства. В этом случае обновления, выполненные в существующих сущностей будет **также** не включать эти отсутствующие свойства. Если для такого свойства существует значение, обновление сбрасывает его в значение по умолчанию для свойства, как определено в источнике данных.  
  
### <a name="creating-projected-types"></a>Создание проецируемых типов  
 В следующем примере используется анонимный запрос LINQ, который проецирует связанные с адресом свойства типа `Customers` в новый тип `CustomerAddress`, как определено на клиенте, и помечается как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressspecific)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressspecific)]  
  
 В этом примере шаблон инициализатора объекта используется для создания нового экземпляра типа `CustmerAddress` вместо вызова конструктора. При проецировании в типы сущностей конструкторы не поддерживаются, но они могут использоваться при проецировании в несущностные типы и в анонимные типы. Поскольку `CustomerAddress` имеет тип сущности, изменения могут быть сделаны и отправлены обратно в службу данных.  
  
 Кроме того, данные из типа `Customer` проецируются в экземпляр типа сущности `CustomerAddress`, а не в анонимный тип. Проецирование в типы сущностей поддерживается, но данные доступны только для чтения, поскольку анонимные типы рассматриваются как несущностные типы.  
  
 Параметры <xref:System.Data.Services.Client.MergeOption> объекта <xref:System.Data.Services.Client.DataServiceContext> используются для разрешения идентификатора во время проекции запроса. Это означает, что, если экземпляр типа `Customer` уже существует в объекте <xref:System.Data.Services.Client.DataServiceContext>, экземпляр `CustomerAddress` с тем же идентификатором будет следовать правилам разрешения идентификатора, установленным параметром <xref:System.Data.Services.Client.MergeOption>  
  
Ниже описываются особенности поведения при проецировании результатов в типы сущностей и несущностным:  

**Создание нового спроецированного экземпляра с помощью инициализаторов**

- Пример

   [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithinitializer)]
   [!code-vb[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithinitializer)]

- Тип сущности: поддерживается

- Тип сущности не: поддерживается

**Создание нового спроецированного экземпляра с помощью конструкторов**

- Пример 

   [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithconstructor)]
   [!code-vb[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithconstructor)]

- Тип объекта: объект <xref:System.NotSupportedException> возникает.

- Тип сущности не: поддерживается

**Использование проекции для преобразования значения свойства**

- Пример

   [!code-csharp[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithtransform)]
   [!code-vb[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithtransform)]
   
- Тип сущности: это преобразование не поддерживается для типов сущности, так как это может привести к путанице, а также возможной переписи данных в источнике данных, к которой принадлежит другой сущности. Вызывается исключение <xref:System.NotSupportedException>.

- Тип сущности не: поддерживается  
  
<a name="considerations"></a>   
## <a name="projection-considerations"></a>Вопросы проекции  
 При определении проекции запроса следует учитывать следующие дополнительные соображения.  
  
-   При определении пользовательских потоков для формата Atom следует убедиться, что все свойства сущностей, имеющие пользовательские сопоставления, включены в проекцию. Если сопоставленное свойство сущности не включено в проекцию, может произойти потеря данных. Дополнительные сведения см. в разделе [настройки веб-канала](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
-   Если вставки выполняются в проецированный тип, который не содержит все свойства сущности в модели данных службы данных, свойства, не включенные в проекцию на клиенте, устанавливаются в их значения по умолчанию.  
  
-   Если обновления выполняются в проецированном типе, который не содержит все свойства сущности в модели данных службы данных, существующие значения, не включенные в проекцию на клиенте, будут переписаны инициализированными значениями по умолчанию.  
  
-   Если проекция включает сложное свойство, должен быть возвращен весь сложный объект.  
  
-   Если проекция включает свойство навигации, связанные объекты загружаются неявно, без вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>. Метод <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> не поддерживается для использования в проецированном запросе.  
  
-   Запросы проецирования запроса на клиенте преобразуются для использования параметра запроса `$select` в URI запроса. Если запрос с проекцией выполняется для предыдущей версии служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], которая не поддерживает параметр запроса `$select`, возвращается ошибка. Это может также произойти, если версия <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> объекта <xref:System.Data.Services.DataServiceBehavior> для службы данных установлена в значение <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1>. Дополнительные сведения см. в разделе [управление версиями службы данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
 Дополнительные сведения см. в разделе [как: спроецировать результаты запроса](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
