---
title: Общие сведения о службах данных WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
ms.openlocfilehash: 66dd61210e36210f5444eb05355612eeb75c155a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790241"
---
# <a name="wcf-data-services-overview"></a>Общие сведения о службах данных WCF
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]обеспечивает создание и использование служб данных для Интернета или интрасети с помощью [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]позволяет предоставлять данные как ресурсы, которые можно использовать для адресации с помощью URI. Это позволяет обращаться к данным и изменять их с использованием семантики REST, в частности стандартных команд HTTP, таких как GET, PUT, POST и DELETE. В этом разделе приведены общие сведения о шаблонах и методиках, определенных службами [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], а также о функциях, предоставляемых службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для использования [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] в приложениях на базе .NET Framework.  
  
## <a name="address-data-as-resources"></a>Адресация данных в виде ресурсов  
 Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставляют данные как ресурсы, адресуемые с помощью URI. Пути к ресурсам формируются на основе соглашений о связи сущностей, описанных в модели EDM. В этой модели сущности представляют операционные единицы данных в домене приложения, такие как клиенты, заказы, элементы и продукты. Дополнительные сведения см. в разделе [EDM](../adonet/entity-data-model.md).  
  
 Адресация ресурсов сущностей в службах [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] осуществляется в виде набора сущностей, содержащего экземпляры типов сущностей. Например, URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders` возвращает все заказы `Northwind` из службы данных, связанные с клиентом, со `CustomerID` значением`ALFKI.`  
  
 Выражения запросов позволяют выполнять традиционные операции с запросами к ресурсам, такие как фильтрация, сортировка и подкачка страниц. Например, URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=Freight gt 50` фильтрует ресурсы, возвращая только заказы со стоимостью транспортировки, превышающей 50 долларов. Дополнительные сведения см. в разделе [доступ к ресурсам службы данных](accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Доступ к данным с возможностью взаимодействия  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]основан на стандартных протоколах Интернета для обеспечения взаимодействия служб данных с приложениями, которые не используют .NET Framework. Так как для адресации данных можно использовать стандартные универсальные коды ресурсов (URI), приложение может получать доступ к данным и изменять их с помощью семантики передачи состояния, в частности стандартных HTTP-глаголов GET, WHERE, POST и DELETE. Это позволяет обращаться к службам из любого клиента, поддерживающего синтаксический анализ и доступ к данным, передаваемым по стандартным протоколам HTTP.  
  
 Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] определяют набор расширений для протокола публикации Atom (AtomPub). Они поддерживают запросы и ответы HTTP в нескольких форматах данных, что позволяет использовать различные клиентские приложения и платформы. Канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] может представлять данные в формате Atom, формате нотации объектов JavaScript (JSON) и в виде простого XML. Atom является форматом по умолчанию. Формат канала указывается в заголовке HTTP-запроса. Дополнительные сведения см. в [разделе OData: Формат](https://go.microsoft.com/fwlink/?LinkID=185794) Atom и [OData: Формат](https://go.microsoft.com/fwlink/?LinkID=185795)JSON.  
  
 При публикации данных в виде [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] веб-канала использует другие существующие Интернет-средства для таких операций, как кэширование и проверка подлинности. Для этого [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируется с существующими ведущими приложениями и службами, такими как ASP.NET, Windows Communication Foundation (WCF) и службы IIS (IIS).  
  
## <a name="storage-independence"></a>Независимость хранилища  
 Хотя ресурсы адресуются на основе модели связей сущностей, службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляют каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] независимо от базового источника данных. После того как службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] принимают запрос HTTP к ресурсу, идентифицируемому URI, запрос десериализуется и его представление передается поставщику [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Поставщик преобразует запрос в формат, зависящий от источника данных, и выполняет его на базовом источнике данных. В службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] независимость от хранилища достигается путем отделения концептуальной модели адресации ресурсов, указанных [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], от конкретной схемы базового источника данных.  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируются со средой ADO.NET Entity Framework, позволяя создавать службы данных, предоставляющие реляционные данные. Для создания модели данных, содержащей адресуемые ресурсы в виде сущностей и в то же время определяющей сопоставление между этой моделью и таблицами нижележащей базы данных, можно использовать программы для работы с моделью EDM. Дополнительные сведения см. в разделе [поставщик Entity Framework](entity-framework-provider-wcf-data-services.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]также позволяет создавать службы данных, которые предоставляют любые структуры данных, возвращающие реализацию <xref:System.Linq.IQueryable%601> интерфейса. Это позволяет создавать службы данных, предоставляющие данные из типов .NET Framework. Для поддержки операций создания, обновления и удаления должен быть также реализован интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [поставщик отражения](reflection-provider-wcf-data-services.md).  
  
 Иллюстрации [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] по интеграции с этими поставщиками данных см. в разделе Схема архитектуры далее в этой статье.  
  
## <a name="custom-business-logic"></a>Пользовательская бизнес-логика  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]упрощает добавление пользовательской бизнес-логики в службу данных с помощью операций службы и перехватчиков. Операции службы — это методы, определенные на сервере и адресуемые с помощью URI в том же формате, что и ресурсы данных. Операции службы могут также использовать синтаксис выражений запросов для фильтрации, упорядочения и разбиения на страницы данных, возвращаемых операцией. Например, URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` представляет вызов служебной операции с именем `GetOrdersByCity` для службы данных Northwind, возвращающей заказы клиентов из Лондона, разбитые на страницы и отсортированные по значению `OrderDate`. Дополнительные сведения см. в разделе [операции службы](service-operations-wcf-data-services.md).  
  
 Перехватчики позволяют разработчику интегрировать настраиваемую прикладную логику в процесс обработки запросов и ответов службы данных. Перехватчики вызываются при выполнении операции запроса, вставки, обновления или удаления над указанным набором сущностей. При этом перехватчик может изменить данные, применить политику проверки подлинности и даже преждевременно завершить операцию. Методы перехватчика необходимо явно регистрировать для конкретного набора сущностей, предоставляемого службой данных. Дополнительные сведения см. в разделе [перехватчики](interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Клиентские библиотеки  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Определяет набор единообразных шаблонов для взаимодействия со службами данных. Это позволяет создавать многократно используемые компоненты, основанные на этих службах, например клиентские библиотеки, которые упрощают использование служб данных.  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают клиентские библиотеки для клиентских приложений как на основе .NET Framework, так и на основе Silverlight. Эти клиентские библиотеки позволяют взаимодействовать со службами данных с помощью объектов .NET Framework. Они также поддерживают запросы на базе объектов и запросы LINQ, загрузку связанных объектов, отслеживание изменений и разрешение идентификаторов. Дополнительные сведения см. в статье [WCF Data Services Client Library](wcf-data-services-client-library.md).  
  
 Помимо [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] клиентских библиотек, поставляемых с .NET Framework и с Silverlight, существуют и другие клиентские библиотеки, которые позволяют [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] использовать веб-канал в клиентских приложениях, таких как приложения PHP, AJAX и Java. Дополнительные сведения см. в [пакете SDK OData](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="architecture-overview"></a>Общие сведения об архитектуре  
 На следующей схеме показана [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] архитектура для [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставления веб-каналов и использования этих каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]в клиентских библиотеках с поддержкой:  
  
 ![Снимок экрана, на котором показана схема архитектуры WCF Data Services.](./media/wcf-data-services-overview/windows-communication-foundation-data-services-architecture.gif)  
  
## <a name="see-also"></a>См. также

- [Службы данных WCF 4.5](index.md)
- [Начало работы](getting-started-with-wcf-data-services.md)
- [Определение служб данных WCF](defining-wcf-data-services.md)
- [Доступ к ресурсам службы данных (WCF Data Services)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd728283(v=vs.100))
- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
- [Передача состояния представления (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
