---
title: "Материализация объектов (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
ms.assetid: f0dbf7b0-0292-4e31-9ae4-b98288336dc1
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f671d3b41e0812916d1db342c211f2db6456ede3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-materialization-wcf-data-services"></a>Материализация объектов (службы данных WCF)
При использовании **добавить ссылку на службу** диалоговое окно, чтобы использовать [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала в приложении клиента на основе .NET Framework, эквивалентные классы данных создаются для каждого типа сущности в модели данных, предоставляемых каналом. Дополнительные сведения см. в разделе [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md). Данные сущности, возвращаемые запросом, материализуются в экземпляр одного из созданных классов клиентской службы данных. Сведения о параметрах слияния и разрешение идентификаторов для отслеживаемых объектов см. в разделе [управление контекстом службы данных](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют также определять собственные классы клиентской службы данных, а не использовать формируемые средством классы данных. Это позволяет разработчикам использовать собственные классы данных, также называемые классами данных POCO (Plain Old CLR Object). При использовании этих типов пользовательских классов данных, следует пометить класс данных с помощью <xref:System.Data.Services.Common.DataServiceKeyAttribute> или <xref:System.Data.Services.Common.DataServiceEntityAttribute> и убедитесь, что имена типов клиента совпадают с именами типов в модели данных службы данных.  
  
 После того, библиотека получает ответное сообщение на запрос, она материализует возвращенные данные из [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала в экземпляры данных клиентских классов службы, имеющие тип запроса. Обычно общий процесс материализации этих объектов происходит следующим образом.  
  
1.  Клиентская библиотека считывает сериализованный тип из элемента `entry` в веб-канале ответных сообщений и пытается создать новый экземпляр правильного типа одним из следующих способов.  
  
    -   Если тип, объявленный в веб-канале, имеет то же имя, что и тип <xref:System.Data.Services.Client.DataServiceQuery%601>, новый экземпляр этого типа создается с помощью пустого конструктора.  
  
    -   Если тип, объявленный в веб-канале, имеет то же имя, что и тип, производный от типа <xref:System.Data.Services.Client.DataServiceQuery%601>, новый экземпляр этого производного типа создается с помощью пустого конструктора.  
  
    -   Если тип, объявленный в веб-канале, не может быть сопоставлен с типом <xref:System.Data.Services.Client.DataServiceQuery%601> или любым производным типом, новый экземпляр запрашиваемого типа создается с помощью пустого конструктора.  
  
    -   Если установлено свойство <xref:System.Data.Services.Client.DataServiceContext.ResolveType%2A>, вызывается предоставленный делегат для переопределения сопоставления типа по умолчанию, основанного на имени, и вместо этого создается новый экземпляр типа, возвращаемого объектом <xref:System.Func%602>. Если этот делегат возвращает значение null, то создается новый экземпляр запрошенного типа. Для поддержки сценария наследования может потребоваться переопределить сопоставление имени типа по умолчанию, основанное на имени.  
  
2.  Клиентская библиотека считывает из элемента `id` объекта `entry` значение URI, которое является значением идентификатора сущности. Если значение <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> объекта <xref:System.Data.Services.Client.MergeOption.NoTracking> не используется, то значение идентификатора используется для отслеживания объекта в <xref:System.Data.Services.Client.DataServiceContext>. Значение идентификатора используется также для обеспечения создания лишь одного экземпляра сущности, даже если сущность возвращается в ответе на запрос несколько раз.  
  
3.  Клиентская библиотека считывает свойства из записи веб-канала и устанавливает соответствующие свойства в только что созданном объекте. Если объект, который имеет то же значение идентификатора, уже присутствует в элементе <xref:System.Data.Services.Client.DataServiceContext>, то свойства устанавливаются в соответствии с параметром <xref:System.Data.Services.Client.MergeOption> элемента <xref:System.Data.Services.Client.DataServiceContext>. Ответ может содержать значения свойств, для которых соответствующее свойство отсутствует в типе клиента. В таком случае выполняемое действие зависит от значения свойства <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> элемента <xref:System.Data.Services.Client.DataServiceContext>. Если свойство равно `true`, то отсутствующее свойство не учитывается. В противном случае произойдет ошибка. Значения свойств устанавливаются следующим образом.  
  
    -   Скалярным свойствам присваивается соответствующее значение записи ответного сообщения.  
  
    -   Сложным свойствам присваивается новый экземпляр сложного типа, принимающий значения свойств сложного типа из ответа.  
  
    -   Свойства навигации, которые возвращают коллекцию связанных сущностей, приравниваются к новому или существующему экземпляру коллекции <xref:System.Collections.Generic.ICollection%601>, где `T` является типом связанной сущности. Эта коллекция будет пустой, если связанные объекты не загружены в объект <xref:System.Data.Services.Client.DataServiceContext>. Дополнительные сведения см. в разделе [загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
        > [!NOTE]
        >  Если созданные классы клиентских данных поддерживают привязку данных, свойства навигации возвращают вместо этого экземпляры класса <xref:System.Data.Services.Client.DataServiceCollection%601>. Дополнительные сведения см. в разделе [привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
4.  Возникает событие <xref:System.Data.Services.Client.DataServiceContext.ReadingEntity>.  
  
5.  Клиентская библиотека присоединяет объект к контексту <xref:System.Data.Services.Client.DataServiceContext>. Если параметр <xref:System.Data.Services.Client.MergeOption> равен <xref:System.Data.Services.Client.MergeOption.NoTracking>, объект не присоединяется.  
  
## <a name="see-also"></a>См. также  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [Проекции запросов](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)
