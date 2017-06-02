---
title: "Обновление службы данных (службы WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, изменение данных"
  - "WCF Data Services, клиентская библиотека"
ms.assetid: 00d993be-ffed-4dea-baf7-6eea982cdb54
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Обновление службы данных (службы WCF Data Services)
При использовании клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для доступа к каналу [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] эта библиотека преобразует записи из канала в экземпляры классов клиентской службы данных.  Эти классы службы данных отслеживаются с помощью контекста <xref:System.Data.Services.Client.DataServiceContext>, к которому относится <xref:System.Data.Services.Client.DataServiceQuery%601>. Клиент отслеживает изменения сущностей, которые включаются в отчет с помощью методов <xref:System.Data.Services.Client.DataServiceContext>.  Эти методы позволяют клиенту отслеживать добавленные и удаленные сущности, а также изменения, вносимые в значения свойств или в связи между экземплярами сущностей.  При вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> отслеженные изменения отправляются назад в службу данных в виде операций, основанных на REST.  
  
> [!NOTE]
>  При использовании экземпляра класса <xref:System.Data.Services.Client.DataServiceCollection%601> для привязки данных к элементам управления, изменения, внесенные в данные с помощью привязанного элемента управления, автоматически передаются объекту <xref:System.Data.Services.Client.DataServiceContext>.  Для получения дополнительной информации см. [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
## Добавление, модификация и изменение сущностей  
 При использовании диалога **Добавление ссылки на службу** в среде Visual Studio для добавления ссылки на канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] все классы сформированной в результате этого клиентской службы данных имеют статический метод *Create*, принимающий один параметр на каждое свойство сущности, не допускающее значения null.  Этот метод можно использовать для создания экземпляров классов типа сущности, как показано в следующем примере.  
  
 [!code-csharp[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#createnewproduct)]
 [!code-vb[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#createnewproduct)]  
  
 Для добавления экземпляра сущности вызовите соответствующий метод *AddTo* класса <xref:System.Data.Services.Client.DataServiceContext>, сформированного диалоговым окном **Добавление ссылки на службу**, как показано в следующем примере.  
  
 [!code-csharp[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addproductspecific)]
 [!code-vb[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addproductspecific)]  
  
 При этом объект добавляется в контекст и в соответствующий набор сущностей.  Можно также вызвать метод <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>, но при этом придется передать имя набора сущностей.  Если добавляемая сущность имеет одну или несколько связей с другими сущностями, можно использовать либо метод <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>, либо один из предыдущих методов и явно задать эти связи.  Эти операции обсуждаются дальше в данном разделе.  
  
 Для изменения существующего экземпляра сущности запросите сущность, произведите необходимые изменения ее свойств, а затем вызовите метод <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> объекта <xref:System.Data.Services.Client.DataServiceContext>, чтобы указать клиентской библиотеке на необходимость отправки обновления объекта, как показано в следующем примере.  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#modifycustomerspecific)]
 [!code-vb[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#modifycustomerspecific)]  
  
 Для удаления экземпляра сущности вызовите метод <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> объекта <xref:System.Data.Services.Client.DataServiceContext>, как показано в следующем примере.  
  
 [!code-csharp[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#deleteproductspecific)]
 [!code-vb[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#deleteproductspecific)]  
  
 Для получения дополнительной информации см. [Как добавлять, перемещать и удалять сущности](../../../../docs/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services.md).  
  
## Присоединение сущностей  
 Клиентская библиотека позволяет сохранить обновления, произведенные в сущности, без выполнения запроса для загрузки сущности в контекст <xref:System.Data.Services.Client.DataServiceContext>.  Используйте метод <xref:System.Data.Services.Client.DataServiceContext.AttachTo%2A> для присоединения существующего объекта к определенному набору сущностей в контексте <xref:System.Data.Services.Client.DataServiceContext>.  Затем этот объект можно изменить и сохранить изменения в службе данных.  В следующем примере измененный пользовательский объект присоединяется к контексту, после чего вызывается метод <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> для пометки присоединенного объекта атрибутом <xref:System.Data.Services.Client.EntityStates> перед вызовом метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobjectspecific)]
 [!code-vb[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobjectspecific)]  
  
 Во время присоединения объектов следует принимать во внимание следующие соображения.  
  
-   Объект присоединяется в состоянии <xref:System.Data.Services.Client.EntityStates>.  
  
-   При присоединении объекта связанные с ним объекты не присоединяются.  
  
-   Объект не может быть присоединен, если сущность уже отслеживается контекстом.  
  
-   При присоединении объекта сущности, полученной со значением eTag, используется перегруженный метод <xref:System.Data.Services.Client.DataServiceContext.AttachTo%28System.String%2CSystem.Object%2CSystem.String%29>, принимающий параметр `etag`.  Это значение eTag используется для проверки параллелизма при сохранении изменений в присоединенном объекте.  
  
 Для получения дополнительной информации см. [Как присоединить имеющуюся сущность к контексту DataServiceContext](../../../../docs/framework/data/wcf/attach-an-existing-entity-to-dc-wcf-data.md).  
  
## Создание и изменение ссылок на связи  
 При добавлении новой сущности с помощью метода <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> или соответствующего метода *AddTo* класса <xref:System.Data.Services.Client.DataServiceContext>, формируемого диалогом **Добавление ссылки на службу**, связи между новой сущностью и связанными сущностями автоматически не определяются.  
  
 Пользователь может создать и изменить связи между экземплярами сущностей и отразить эти изменения в службе данных с помощью клиентской библиотеки.  Связи между сущностями определяются как ассоциации модели, а объект <xref:System.Data.Services.Client.DataServiceContext> отслеживает каждую связь в виде объекта ссылки в контексте.  Для создания, изменения и удаления ссылок в [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] имеются следующие методы класса <xref:System.Data.Services.Client.DataServiceContext>.  
  
|Метод|Описание|  
|-----------|--------------|  
|<xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>|Создает новую ссылку между двумя связанными объектами сущностей.  Вызов этого метода эквивалентен вызову <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> и <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> и позволяет создать новый объект и определить связь с существующим объектом.|  
|<xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>|Создает новую ссылку между двумя связанными объектами сущностей.|  
|<xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>|Обновляет существующую связь между двумя объектами связанной сущности.  <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> также используется для удаления связи с количеством элементов «0 или 1 к 1» \(`0..1:1`\) и «1 к 1» \(`1:1`\).  Это можно сделать, задав связанному объекту значение `null`.|  
|<xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A>|Помечает ссылку, отслеживаемую контекстом, для удаления при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  Используйте этот метод при удалении связанного объекта или изменения связи путем удаления ссылки на существующий объект и последующего добавления ссылки на другой связанный объект.|  
|<xref:System.Data.Services.Client.DataServiceContext.AttachLink%2A>|Уведомляет контекст о существовании ссылки между двумя объектами сущностей.  Контекст предполагает, что эта связь уже существует в службе данных, и не пытается создать связь при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  Используйте этот метод при присоединении объектов к контексту, если необходимо также присоединить ссылку между двумя из них.  При определении новой связи лучше использовать объект <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>.|  
|<xref:System.Data.Services.Client.DataServiceContext.DetachLink%2A>|Прекращает отслеживание указанной ссылки в контексте.  Этот метод используется для удаления связей «один ко многим» \(`*:*`\).  Для связей с количеством элементов, равным одному, следует использовать объект <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>.|  
  
 Следующий пример иллюстрирует использование метода <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> для добавления нового объекта `Order_Detail`, связанного с имеющейся сущностью `Orders`.  Поскольку новый объект `Order_Details` отслеживается с помощью метода <xref:System.Data.Services.Client.DataServiceContext>, связь добавленного объекта `Order_Details` с существующей сущностью `Products` определяется методом<xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>:  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderspecific)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderspecific)]  
  
 В то время как метод <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> определяет связи, которые необходимо создать в службе данных, чтобы эти связи были отражены в объектах, присутствующих в контексте, для самих объектов необходимо задать свойства навигации.  В предыдущем примере необходимо задать свойства навигации следующим образом.  
  
 [!code-csharp[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#setnavprops)]
 [!code-vb[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#setnavprops)]  
  
 Для получения дополнительной информации см. [Как определять связи сущностей](../../../../docs/framework/data/wcf/how-to-define-entity-relationships-wcf-data-services.md).  
  
## Сохранение изменений  
 Изменения отслеживаются в экземпляре <xref:System.Data.Services.Client.DataServiceContext>, но не отправляются на сервер немедленно.  После завершения изменений для указанного действия вызовите метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>, чтобы передать все изменения в службу данных.  Для получения дополнительной информации см. [Управление контекстом службы данных](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  Изменения можно сохранить и асинхронно с помощью методов <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A> и <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>.  Для получения дополнительной информации см. [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)   
 [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)   
 [Пакетные операции](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)   
 [Материализация объектов](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)   
 [Управление контекстом службы данных](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)