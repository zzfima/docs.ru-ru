---
title: Загрузка отложенного содержимого (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 32f9b588-c832-44c4-a7e0-fcce635df59a
ms.openlocfilehash: 811118755c4688bd0ea8cb9ba37b2101ab6c52cf
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568944"
---
# <a name="loading-deferred-content-wcf-data-services"></a>Загрузка отложенного содержимого (службы данных WCF)
По умолчанию WCF Data Services ограничивает объем данных, возвращаемых запросом. Однако при необходимости из службы данных можно явно загрузить дополнительные данные, включая связанные сущности, разбитые на страницы данные ответа и потоки двоичных данных. Этот раздел описывает загрузку такого отложенного содержимого в приложении.  
  
## <a name="related-entities"></a>Связанные сущности  
 При выполнении запроса возвращаются только сущности в адресованном наборе сущностей. Например, когда запрос к службе данных Northwind возвращает сущности `Customers`, по умолчанию возврат связанных сущностей `Orders` не происходит, несмотря на наличие связи между сущностями `Customers` и `Orders`. Кроме того, если в службе данных включена подкачка, необходимо явно загружать последующие страницы данных из службы. Существует два способа загрузки связанных сущностей.  
  
- **Упреждающая загрузка**. можно использовать параметр запроса `$expand`, чтобы запросить возвращение сущностей, связанных ассоциацией, с набором сущностей, запрошенных запросом. Для добавления параметра <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> в запрос, отправляемый службе данных, используйте метод <xref:System.Data.Services.Client.DataServiceQuery%601> класса `$expand`. Несколько связанных наборов сущностей можно запросить, разделяя их запятыми, как показывает следующий пример. Все сущности, запрашиваемые в запросе, возвращаются в одном ответе. Следующий пример возвращает сущности `Order_Details` и `Customers` вместе с набором сущностей `Orders`:  
  
     [!code-csharp[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetailsspecific)]  
  
     WCF Data Services ограничивается 12 количеством наборов сущностей, которые могут быть добавлены в один запрос с помощью параметра запроса `$expand`.  
  
- **Явная загрузка**. для явной загрузки связанных сущностей можно вызвать метод <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> в экземпляре <xref:System.Data.Services.Client.DataServiceContext>. При каждом вызове метода <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> создается отдельный запрос к службе данных. Следующий пример явно загружает сущности `Order_Details` для сущности `Orders`:  
  
     [!code-csharp[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedorderdetailsspecific)]  
  
 При выборе параметра помните, что придется соблюдать баланс между числом запросов к службе данных и объемом данных, возвращаемых в одном ответе. Активная загрузка используется, если приложению требуются связанные объекты и необходимо избежать дополнительной задержки, связанной с дополнительными запросами для явного извлечения данных. Однако в тех случаях, когда приложению требуются только данные для конкретных связанных экземпляров сущности, рассмотрите возможность их явной загрузки путем вызова метода <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>. Дополнительные сведения см. [в разделе инструкции. Загрузка связанных сущностей](how-to-load-related-entities-wcf-data-services.md).  
  
## <a name="paged-content"></a>Содержимое, разбитое на страницы  
 Если в службе данных включена подкачка страниц, число сущностей в канале, возвращаемом службой данных, ограничено настройками службы данных. Пределы подкачки можно задавать отдельно для каждого набора сущностей. Дополнительные сведения см. [в разделе Настройка службы данных](configuring-the-data-service-wcf-data-services.md). Если включена подкачка страниц, то последняя запись в канале содержит ссылку на следующую страницу данных. Эта ссылка содержится в объекте <xref:System.Data.Services.Client.DataServiceQueryContinuation%601>. Получить URI для следующей страницы можно, вызвав метод <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> объекта <xref:System.Data.Services.Client.QueryOperationResponse%601>, возвращенного при выполнении запроса <xref:System.Data.Services.Client.DataServiceQuery%601>. Возвращенный объект <xref:System.Data.Services.Client.DataServiceQueryContinuation%601> можно затем использовать для загрузки следующей страницы результатов. Перед вызовом метода <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> результат запроса надо перечислить. Рассмотрите возможность применения цикла `do…while`, чтобы сначала перечислить результат запроса, а потом проверить следующее значение ссылки на `non-null`. Если метод <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> возвращает `null` (`Nothing` в Visual Basic), дополнительные страницы результата для исходного запроса отсутствуют. Следующий пример показывает цикл `do…while`, который загружает разбитые на страницы данные клиентов из образца службы данных Northwind.  
  
 [!code-csharp[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadnextlink)]
 [!code-vb[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadnextlink)]  
  
 Если запрос требует возвращения связанных сущностей в одном ответе вместе с запрошенным набором сущностей, пределы разбиения на страницы могут повлиять на вложенные каналы, встроенные вместе с запросом. Например, если в образце службы данных Northwind установлен предел подкачки для набора сущностей `Customers`, независимый предел подкачки может быть также установлен для набора сущностей `Orders`, как в следующем примере из файла Northwind.svc.cs, определяющего образец службы данных Northwind.  
  
 [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
 [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
 В этом случае необходимо реализовать подкачку как для канала верхнего уровня `Customers`, так и для вложенного канала сущностей `Orders`. Следующий пример показывает цикл `while`, используемый для загрузки страниц сущностей `Orders`, связанных с выбранной сущностью `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadnextorderslink)]
 [!code-vb[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadnextorderslink)]  
  
 Дополнительные сведения см. [в разделе как загружать выгруженные результаты](how-to-load-paged-results-wcf-data-services.md).  
  
## <a name="binary-data-streams"></a>Потоки двоичных данных  
 WCF Data Services позволяет обращаться к данным больших двоичных объектов (BLOB) как к потоку данных. Преобразование в поток откладывает загрузку двоичных данных до момента, когда они понадобятся, а клиент имеет возможность обработать их более эффективно. Чтобы можно было воспользоваться этой функцией, в службе данных должен быть реализован поставщик <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Дополнительные сведения см. в разделе [Streaming Provider](streaming-provider-wcf-data-services.md). Если потоки включены, типы сущностей возвращаются без связанных двоичных данных. В этом случае необходимо использовать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> класса <xref:System.Data.Services.Client.DataServiceContext>, чтобы получить доступ к потоку данных для двоичных данных из службы. Аналогично можно использовать метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> для добавления или изменения двоичных данных сущности в виде потока. Дополнительные сведения см. в разделе [Работа с двоичными данными](working-with-binary-data-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также:

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
- [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)
