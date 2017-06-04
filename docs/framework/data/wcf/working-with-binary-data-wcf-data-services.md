---
title: "Работа с двоичными данными (службы WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, двоичные данные"
  - "WCF Data Services, потоки"
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Работа с двоичными данными (службы WCF Data Services)
Клиентская библиотека [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет извлекать и обновлять двоичные данные из канала [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] одним из следующих способов:  
  
-   В качестве свойства сущности примитивного типа.  Этот метод рекомендуется использовать при работе с небольшими двоичными объектами данных, которые могут быть легко загружены в память.  В этом случае двоичное свойство представляет собой свойство сущности, предоставленное моделью данных, служба данных сериализует двоичные данные в ответном сообщении как XML\-элемент с двоичной кодировкой с базой 64.  
  
-   В качестве отдельного потока двоичных данных.  Этот метод рекомендуется использовать для доступа и изменения данных больших двоичных объектов, которые могут представлять фото, видео или другие типы данных с двоичной кодировкой.  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] реализуют потоки двоичных данных с помощью HTTP в соответствии с определением в [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  В этом подходе двоичные данные обрабатываются как медиаресурс, отделенный, но при этом связанный с сущностью, которая называется медиассылкой.  Для получения дополнительной информации см. [Потоковый поставщик](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
> [!TIP]
>  Пошаговые инструкции по созданию клиентского приложения [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)], загружающего двоичные файлы изображений из службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], которая хранит изображения, см. в сообщении [Последовательности поточных поставщиков служб данных, часть 2. Доступ к потоку медиаресурса с клиента](http://go.microsoft.com/fwlink/?LinkId=201637).  Сведения о загрузке образца кода для потоковой службы данных с изображениями, о которой идет речь в сообщении блога, см. в разделе [Образец потоковой службы данных с изображениями](http://go.microsoft.com/fwlink/?LinkId=198988) на сайте MSDN Code Gallery.  
  
## Метаданные сущности  
 Сущность со связанным потоком медиаисточника указывается в метаданных службы данных с помощью атрибута `HasStream`, применяемого к типу сущности, который является ссылкой на данные.  В следующем примере сущность `PhotoInfo` — это ссылка на связанный медиаресурс, указанный атрибутом `HasStream`.  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria photo streaming service/xml/photodata.edmx#hasstream)]  
  
 В остальных примерах этого раздела описываются способы доступа к потоку медиаресурса и его изменения.  Полный пример получения потока медиаресурса в клиентском приложении .NET Framework с помощью клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] см. в сообщении [Получение доступа к потоку медиаресурса с клиента](http://go.microsoft.com/fwlink/?LinkID=201637).  
  
## Получение доступа к потоку двоичных данных  
 Клиентская библиотека [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляет методы доступа к потокам двоичных данных из службы данных на основе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  При загрузке медиаресурса можно использовать URI\-идентификатор медиаресурса или получить двоичный поток, непосредственно содержащий данные медиаресурса.  Можно также загрузить данные медиаресурса в виде двоичного потока.  
  
> [!TIP]
>  Пошаговые инструкции по созданию клиентского приложения [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)], загружающего двоичные файлы изображений из службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], которая хранит изображения, см. в сообщении [Последовательности поточных поставщиков служб данных, часть 2. Доступ к потоку медиаресурса с клиента](http://go.microsoft.com/fwlink/?LinkId=201637).  Сведения о загрузке образца кода для потоковой службы данных с изображениями, о которой идет речь в сообщении блога, см. в разделе [Образец потоковой службы данных с изображениями](http://go.microsoft.com/fwlink/?LinkId=198988) на сайте MSDN Code Gallery.  
  
### Получение URI\-идентификатора двоичного потока  
 При получении определенных типов медиаресурсов, таких как изображения и другие медиафайлы, часто бывает проще использовать URI\-идентификатор приложения, чем обрабатывать непосредственно источник двоичных данных.  Чтобы получить URI\-идентификатор потока ресурса, связанный с определенной ссылкой на данные, следует вызвать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> для экземпляра <xref:System.Data.Services.Client.DataServiceContext>, который отслеживает сущность.  В этом примере показан порядок вызова метода <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A>, получающего URI\-идентификатор потока медиаресурса, который используется для создания нового изображения на стороне клиента.  
  
 [!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming client/cs/photowindow.xaml.cs#getreadstreamuri)]
 [!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming client/vb/photowindow.xaml.vb#getreadstreamuri)]  
  
### Загрузка двоичного потока ресурса  
 При получении двоичного потока ресурса следует вызвать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> для экземпляра <xref:System.Data.Services.Client.DataServiceContext>, который отслеживает ссылку на данные.  Этот метод отправляет запрос службе данных, возвращающей объект <xref:System.Data.Services.Client.DataServiceStreamResponse>, который содержит ссылку на поток, содержащий медиаресурс.  Этот метод используется, если приложение требует двоичный файл ресурса в виде <xref:System.IO.Stream>.  В следующем примере показано, как вызвать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> для получения потока, используемого для создания нового изображения на стороне клиента.  
  
 [!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria streaming client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
 [!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria streaming client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]  
  
> [!NOTE]
>  Заголовок Content\-Length в ответном сообщении, в котором содержится поток двоичных данных, не заданный службой данных.  Это значение может не отражать фактическую длину потока двоичных данных.  
  
### Передача медиаресурса в виде потока  
 Чтобы вставить или обновить медиаресурс, вызовите метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> для экземпляра <xref:System.Data.Services.Client.DataServiceContext>, который отслеживает сущность.  Этот метод отправляет запрос службе данных, содержащей медиаресурс, считанный из предоставленного потока.  В следующем примере показано, как вызвать метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>, чтобы отправить изображение в службу данных.  
  
 [!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming client/cs/photodetailswindow.xaml.cs#setsavestream)]
 [!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming client/vb/photodetailswindow.xaml.vb#setsavestream)]  
  
 В этом примере метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> вызывается с помощью присвоения значения `true` параметру `closeStream`.  Благодаря этому объект <xref:System.Data.Services.Client.DataServiceContext> гарантированно закрывает поток после загрузки двоичных данных в службу данных.  
  
> [!NOTE]
>  При вызове метода <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> поток не отправляется в службу данных, пока не будет вызван метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)