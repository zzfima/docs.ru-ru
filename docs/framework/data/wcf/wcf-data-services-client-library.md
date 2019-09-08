---
title: Библиотека клиентов служб данных WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 545442b0086361c8ce8c0482801afc10b1fee96e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779678"
---
# <a name="wcf-data-services-client-library"></a>Библиотека клиентов служб данных WCF
Со службами данных, основанными на [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], может взаимодействовать любое приложение, которое способно отправить HTTP-запрос и обработать канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], возвращаемый службой данных. Эта возможность взаимодействия позволяет обращаться к службам, основанным на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], из широкого спектра веб-приложений. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]включает клиентские библиотеки, обеспечивающие более широкие возможности программирования при использовании [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналов из .NET Framework или приложений на основе Silverlight.  
  
 Клиентская библиотека содержит два основных класса: <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>. Класс <xref:System.Data.Services.Client.DataServiceContext> инкапсулирует операции, поддерживающие работу с конкретной службой данных. Хотя службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] не сохраняют состояние, контекст его сохраняет. Таким образом, <xref:System.Data.Services.Client.DataServiceContext> класс можно использовать для поддержания состояния на стороне клиента между взаимодействием со службой данных для поддержки таких функций, как управление изменениями. Этот класс также управляет идентификаторами и отслеживает изменения. Класс <xref:System.Data.Services.Client.DataServiceQuery%601> представляет запрос к определенному набору сущностей.  
  
 Этот раздел описывает использование клиентских библиотек для доступа и изменения данных из клиентского приложения .NET Framework. Дополнительные сведения об использовании клиентской библиотеки с [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] приложением на основе Silverlight см. в разделе [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016). Доступны другие клиентские библиотеки, которые позволяют использовать [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канал в приложениях других типов. Дополнительные сведения см. в [пакете SDK OData](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание библиотеки клиентов службы данных](generating-the-data-service-client-library-wcf-data-services.md)  
 Описывает, как создать клиентскую библиотеку и клиентские классы службы данных, основанные [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] на веб-каналах.  
  
 [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)  
 Описывает выполнение запросов к службе данных из приложения на основе .NET Framework с помощью клиентских библиотек.  
  
 [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md)  
 Описывает загрузку дополнительного содержимого, не включенного в первоначальный ответ на запрос.  
  
 [Обновление службы данных](updating-the-data-service-wcf-data-services.md)  
 Описывает создание, изменение и удаление сущностей и отношений с помощью клиентских библиотек.  
  
 [Асинхронные операции](asynchronous-operations-wcf-data-services.md)  
 Описывает возможности, предоставляемые клиентскими библиотеками для асинхронной работы со службой данных.  
  
 [Пакетные операции](batching-operations-wcf-data-services.md)  
 Описывает отправку нескольких запросов к службе данных в одном пакете с помощью клиентских библиотек.  
  
 [Привязка данных к элементам управления](binding-data-to-controls-wcf-data-services.md)  
 Описывает, как привязать элементы управления [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] к веб-каналу, возвращенному службой данных.  
  
 [Вызов операций служб](calling-service-operations-wcf-data-services.md)  
 Описывает, как использовать клиентскую библиотеку для вызова операций службы.  
  
 [Управление контекстом службы данных](managing-the-data-service-context-wcf-data-services.md)  
 Описывает параметры управления режимом работы клиентской библиотеки.  
  
 [Работа с двоичными данными](working-with-binary-data-wcf-data-services.md)  
 Описывает доступ к двоичным данным, возвращенным службой данных в виде потока данных, и их изменение.  
  
## <a name="see-also"></a>См. также

- [Определение служб данных WCF](defining-wcf-data-services.md)
- [Начало работы](getting-started-with-wcf-data-services.md)
