---
title: Библиотека клиентов служб данных WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 5d14a1be3cd40ace2e31fec6f44a86707e5c4476
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875203"
---
# <a name="wcf-data-services-client-library"></a>Библиотека клиентов служб данных WCF
Со службами данных, основанными на [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], может взаимодействовать любое приложение, которое способно отправить HTTP-запрос и обработать канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], возвращаемый службой данных. Эта возможность взаимодействия позволяет обращаться к службам, основанным на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], из широкого спектра веб-приложений. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включает в себя клиентские библиотеки, предоставляющие более широкие возможности программирования, при использовании [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналов из .NET Framework или приложений на основе Silverlight.  
  
 Клиентская библиотека содержит два основных класса: <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>. Класс <xref:System.Data.Services.Client.DataServiceContext> инкапсулирует операции, поддерживающие работу с конкретной службой данных. Хотя службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] не сохраняют состояние, контекст его сохраняет. Таким образом, можно использовать <xref:System.Data.Services.Client.DataServiceContext> класса для поддержания состояния на стороне клиента между взаимодействиями со службой данных для поддержки функции, такие как управление изменениями. Этот класс также управляет идентификаторами и отслеживает изменения. Класс <xref:System.Data.Services.Client.DataServiceQuery%601> представляет запрос к определенному набору сущностей.  
  
 Этот раздел описывает использование клиентских библиотек для доступа и изменения данных из клиентского приложения .NET Framework. Дополнительные сведения об использовании [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] клиентской библиотеки с приложением на основе Silverlight см. в разделе [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016). Доступны другие клиентские библиотеки, позволяющие использовать [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала в приложениях других видов. Дополнительные сведения см. в разделе [OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 Описывает создание клиентской библиотеки и клиентские классы службы данных, основанных на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналов.  
  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 Описывает выполнение запросов к службе данных из приложения на основе .NET Framework с помощью клиентских библиотек.  
  
 [Загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 Описывает загрузку дополнительного содержимого, не включенного в первоначальный ответ на запрос.  
  
 [Обновление службы данных](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 Описывает создание, изменение и удаление сущностей и отношений с помощью клиентских библиотек.  
  
 [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 Описывает возможности, предоставляемые клиентскими библиотеками для асинхронной работы со службой данных.  
  
 [Пакетные операции](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 Описывает отправку нескольких запросов к службе данных в одном пакете с помощью клиентских библиотек.  
  
 [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 Описывает, как привязать элементы управления к [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канале, возвращаемых службой данных.  
  
 [Вызов операций служб](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 Описывает, как использовать клиентскую библиотеку для вызова операций службы.  
  
 [Управление контекстом службы данных](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 Описывает параметры управления режимом работы клиентской библиотеки.  
  
 [Работа с двоичными данными](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 Описывает доступ к двоичным данным, возвращенным службой данных в виде потока данных, и их изменение.  
  
## <a name="see-also"></a>См. также

- [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
