---
title: "Доступ к ресурсам служб данных (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dddbd9cf8e11f09cf1c2dc36db49281d00e97aac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Доступ к ресурсам служб данных (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]поддерживает [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для предоставления данных в виде канала с ресурсами, которые адресуются по URI. Эти ресурсы представлены в соответствии с соглашениями отношения сущностей из [модели EDM](../../../../docs/framework/data/adonet/entity-data-model.md). Сущности в этой модели представляют операционные единицы данных, которые являются типами данных в домене приложений, такими как клиенты, заказы, элементы и продукты. Это позволяет обращаться к данным сущности и изменять их с использованием семантики REST, в частности стандартных команд HTTP, таких как GET, PUT, POST и DELETE.  
  
## <a name="addressing-resources"></a>Обращение к ресурсам  
 В службах [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] обращение к данным, предоставленным моделью данных, осуществляется с использованием URI. Например следующий URI возвращает канал набора сущностей Customers, который содержит записи для всех экземпляров типа сущности Customer:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Сущности имеют специальные свойства, называемые ключами сущностей. Ключ сущности используется для уникальной идентификации одной сущности в наборе сущностей. Это позволяет адресовать конкретный экземпляр типа сущности в наборе сущностей. Например, следующий URI возвращает запись для определенного экземпляра типа сущности Customer, имеющего значение ключа `ALFKI`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 К свойствам примитивного типа и сложным свойствам экземпляра сущности можно обращаться по отдельности. Например, следующий URI возвращает XML-элемент, содержащий значение свойства `ContactName` для конкретной сущности Customer:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 При включении конечной точки `$value` в предыдущий URI в ответном сообщении возвращается только значение свойства примитивного типа. В следующем примере возвращается только строка «Maria Anders» без XML-элемента:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Связи между сущностями определяются в модели данных с помощью ассоциаций. Эти ассоциации позволяют адресовать набор связанных сущностей с помощью свойств навигации экземпляра сущности. Свойство навигации возвращает либо одну связанную сущность в случае связи «многие к одному», либо набор связанных сущностей в случае связи «один ко многим». Например, следующий URI возвращает канал, который представляет набор всех заказов, связанных с конкретной сущностью Customer:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Связи, которые обычно являются двунаправленными, представлены парой свойств навигации. В отличие от связей, описанных в предыдущем примере, следующий URI возвращает ссылку на сущность Customer, к которой принадлежит определенная сущность Order:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]также обеспечивает для адресации ресурсов на основе результатов выражений запросов. Это дает возможность фильтровать наборы ресурсов на основе вычисленного выражения. Например, следующий URI фильтрует для возврата только заказы конкретного клиента, доставленные с 22 сентября 1997 г.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Дополнительные сведения см. в разделе [OData: соглашения URI](http://go.microsoft.com/fwlink/?LinkId=185564).  
  
## <a name="system-query-options"></a>Параметры запросов системы  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Определяет набор системных параметров запросов, которые можно использовать для выполнения традиционных операций с запросами к ресурсам, например фильтрации, сортировки и разбиения на страницы. Например, следующий URI возвращает набор всех `Order` сущности, вместе со связанными `Order_Detail` сущностей, почтовые коды которых не заканчиваются на `100`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Записи в возвращаемом канале упорядочены по значению свойства заказов ShipCity.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]поддерживает следующие [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] системные параметры запросов:  
  
|Параметр запроса|Описание|  
|------------------|-----------------|  
|`$orderby`|Определяет порядок сортировки по умолчанию для сущностей в возвращенном канале. Следующий запрос упорядочивает возвращаемый канал Customers по странам и городам:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Дополнительные сведения см. в разделе [OData: параметр системного запроса OrderBy ($orderby)](http://go.microsoft.com/fwlink/?LinkId=186968).|  
|`$top`|Указывает количество сущностей, которые необходимо включить в возвращаемый канал. В следующем примере пропускаются первые 10 клиентов и возвращаются следующие 10:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Дополнительные сведения см. в разделе [OData: параметр системного запроса ($top)](http://go.microsoft.com/fwlink/?LinkId=186969).|  
|`$skip`|Указывает количество сущностей, которые необходимо пропустить перед возвратом сущностей в канал. В следующем примере пропускаются первые 10 клиентов и возвращаются следующие 10:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Дополнительные сведения см. в разделе [OData: параметр пропуска системного запроса ($skip)](http://go.microsoft.com/fwlink/?LinkId=186971).|  
|`$filter`|Определяет выражение, фильтрующее сущности, которые возвращаются в канал на основе определенного критерия. Этот параметр запроса поддерживает набор операторов логического сравнения, арифметических операторов и заранее заданных функций запроса, которые используются для оценки критерия фильтра. В следующем примере возвращаются все заказы, почтовые коды которых не оканчиваются на 100:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Дополнительные сведения см. в разделе [OData: параметр системного запроса фильтрации ($filter)](http://go.microsoft.com/fwlink/?LinkId=186972).|  
|`$expand`|Указываются связанные сущности, возвращаемые запросом. Связанные сущности включаются либо в качестве канала, либо в качестве записи, встроенной в сущность, возвращаемую запросом. В следующем примере возвращается заказ для клиента «ALFKI» вместе со сведениями по всем заказам:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Дополнительные сведения см. в разделе [OData: параметр системного запроса ($expand)](http://go.microsoft.com/fwlink/?LinkId=186973).|  
|`$select`|Указывает проекцию, определяющую свойства сущности, возвращаемые в проекции. По умолчанию в канале возвращаются все свойства сущности. В следующем запросе возвращается только три свойства сущности `Customer`:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Дополнительные сведения см. в разделе [OData: параметр системного запроса ($select)](http://go.microsoft.com/fwlink/?LinkID=186076).|  
|`$inlinecount`|Запрашивает включение в поток количества сущностей, возвращаемых в канале. Дополнительные сведения см. в разделе [OData: параметр системного запроса Inlinecount ($inlinecount)](http://go.microsoft.com/fwlink/?LinkId=186975).|  
  
## <a name="addressing-relationships"></a>Адресация связей  
 Помимо адресация наборов сущностей и экземпляров сущности [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] также позволяет ассоциациям, представляющим связи между сущностями. Эта функциональность необходима для создания или изменения связей между двумя экземплярами сущностей, таких как поставщик, связанный с данным заказом в образце базы данных Northwind. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]поддерживает `$link` оператор, чтобы адресовать сопоставления между сущностями. Например, следующий URI задан в сообщении запроса HTTP PUT для изменения поставщика конкретного заказа на нового.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Дополнительные сведения см. в разделе [OData: обращение к ссылкам между записями](http://go.microsoft.com/fwlink/?LinkId=187351).  
  
## <a name="consuming-the-returned-feed"></a>Использование возвращаемого канала  
 URI [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ресурсов позволяет адресовать данные сущности, предоставляемые службой. При вводе URI в поле адреса веб-браузера, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] возвращается представление запрошенного ресурса веб-канала. Дополнительные сведения см. в разделе [кратком руководстве по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Хотя веб-браузера можно проверить, возвращает ресурса службы данных нужные данные, производственным службам данных, которые также можно создавать, обновлять и удалять данные, обычно осуществляется код приложения или языков на веб-странице скриптов. Дополнительные сведения см. в разделе [использование служб данных в клиентском приложении](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Веб-сайт протокола Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=182204)
