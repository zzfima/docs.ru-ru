---
title: Работа с двоичными данными (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, binary data
- WCF Data Services, streams
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
ms.openlocfilehash: e088383adf2345f9a2698d0f8794765461cdbaad
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975015"
---
# <a name="working-with-binary-data-wcf-data-services"></a>Работа с двоичными данными (службы данных WCF)

Клиентская библиотека [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет извлекать и обновлять двоичные данные из канала Open Data Protocol (OData) одним из следующих способов:

- В качестве свойства сущности примитивного типа. Этот метод рекомендуется использовать при работе с небольшими двоичными объектами данных, которые могут быть легко загружены в память. В этом случае двоичное свойство представляет собой свойство сущности, предоставленное моделью данных, служба данных сериализует двоичные данные в ответном сообщении как XML-элемент с двоичной кодировкой с базой 64.

- В качестве отдельного потока двоичных данных. Этот метод рекомендуется использовать для доступа и изменения данных больших двоичных объектов, которые могут представлять фото, видео или другие типы данных с двоичной кодировкой.

[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] реализует потоковую передачу двоичных данных с помощью HTTP, как определено в OData. В этом механизме двоичные данные обрабатываются как ресурс мультимедиа, отличный от, но связанный с сущностью, которая называется записью ссылки на носитель. Дополнительные сведения см. в разделе [Streaming Provider](streaming-provider-wcf-data-services.md).

> [!TIP]
> Пошаговый пример создания клиентского приложения Windows Presentation Foundation (WPF), которое скачивает двоичные файлы изображений из службы OData, в которой хранятся фотографии, см. в разделе Post [Data Services Streaming Provider Series (часть 2): доступ к потоку ресурсов мультимедиа от клиента](https://go.microsoft.com/fwlink/?LinkId=201637). Чтобы скачать пример кода для службы данных Photo фото, как показано в записи блога, см. [Пример потоковой передачи Photo Data](https://go.microsoft.com/fwlink/?LinkId=198988) Service в коллекции кода MSDN.

## <a name="entity-metadata"></a>Метаданные сущности

Сущность со связанным потоком медиаисточника указывается в метаданных службы данных с помощью атрибута `HasStream`, применяемого к типу сущности, который является ссылкой на данные. В следующем примере сущность `PhotoInfo` — это запись ссылки на носитель, которая содержит связанный ресурс мультимедиа, обозначенный атрибутом `HasStream`.

[!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]

В остальных примерах этого раздела описываются способы доступа к потоку медиаресурса и его изменения. Полный пример использования потока ресурсов мультимедиа в клиентском приложении .NET Framework с помощью клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] см. в разделе Передача [доступа к потоку ресурсов мультимедиа от клиента](https://go.microsoft.com/fwlink/?LinkID=201637).

## <a name="accessing-the-binary-resource-stream"></a>Получение доступа к потоку двоичных данных

Клиентская библиотека [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляет методы для доступа к потокам двоичных ресурсов из службы данных на основе OData. При загрузке медиаресурса можно использовать URI-идентификатор медиаресурса или получить двоичный поток, непосредственно содержащий данные медиаресурса. Можно также загрузить данные медиаресурса в виде двоичного потока.

> [!TIP]
> Пошаговый пример создания клиентского приложения Windows Presentation Foundation (WPF), которое скачивает двоичные файлы изображений из службы OData, в которой хранятся фотографии, см. в разделе Post [Data Services Streaming Provider Series (часть 2): доступ к потоку ресурсов мультимедиа от клиента](https://go.microsoft.com/fwlink/?LinkId=201637). Чтобы скачать пример кода для службы данных Photo фото, как показано в записи блога, см. [Пример потоковой передачи Photo Data](https://go.microsoft.com/fwlink/?LinkId=198988) Service в коллекции кода MSDN.

### <a name="getting-the-uri-of-the-binary-stream"></a>Получение URI-идентификатора двоичного потока

При получении определенных типов медиаресурсов, таких как изображения и другие медиафайлы, часто бывает проще использовать URI-идентификатор приложения, чем обрабатывать непосредственно источник двоичных данных. Чтобы получить URI-идентификатор потока ресурса, связанный с определенной ссылкой на данные, следует вызвать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> для экземпляра <xref:System.Data.Services.Client.DataServiceContext>, который отслеживает сущность. В этом примере показан порядок вызова метода <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A>, получающего URI-идентификатор потока медиаресурса, который используется для создания нового изображения на стороне клиента.

[!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photowindow.xaml.cs#getreadstreamuri)]
[!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photowindow.xaml.vb#getreadstreamuri)]

### <a name="downloading-the-binary-resource-stream"></a>Загрузка двоичного потока ресурса

При получении двоичного потока ресурса следует вызвать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> для экземпляра <xref:System.Data.Services.Client.DataServiceContext>, который отслеживает ссылку на данные. Этот метод отправляет запрос службе данных, возвращающей объект <xref:System.Data.Services.Client.DataServiceStreamResponse>, который содержит ссылку на поток, содержащий медиаресурс. Этот метод используется, если приложение требует двоичный файл ресурса в виде <xref:System.IO.Stream>. В следующем примере показано, как вызвать метод <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> для получения потока, используемого для создания нового изображения на стороне клиента.

[!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_streaming_client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
[!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_streaming_client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]

> [!NOTE]
> Заголовок Content-Length в ответном сообщении, в котором содержится поток двоичных данных, не заданный службой данных. Это значение может не отражать фактическую длину потока двоичных данных.

### <a name="uploading-a-media-resource-as-a-stream"></a>Передача медиаресурса в виде потока

Чтобы вставить или обновить медиаресурс, вызовите метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> для экземпляра <xref:System.Data.Services.Client.DataServiceContext>, который отслеживает сущность. Этот метод отправляет запрос службе данных, содержащей медиаресурс, считанный из предоставленного потока. В следующем примере показано, как вызвать метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>, чтобы отправить изображение в службу данных.

[!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photodetailswindow.xaml.cs#setsavestream)]
[!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photodetailswindow.xaml.vb#setsavestream)]

В этом примере метод <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> вызывается с помощью присвоения значения `true` параметру `closeStream`. Благодаря этому объект <xref:System.Data.Services.Client.DataServiceContext> гарантированно закрывает поток после загрузки двоичных данных в службу данных.

> [!NOTE]
> При вызове метода <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> поток не отправляется в службу данных, пока не будет вызван метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.

## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
- [Привязка данных к элементам управления](binding-data-to-controls-wcf-data-services.md)
