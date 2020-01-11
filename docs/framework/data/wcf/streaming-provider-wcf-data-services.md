---
title: Потоковый поставщик (службы WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, binary data
- streaming data provider [WCF Data Services]
- WCF Data Services, streams
ms.assetid: f0978fe4-5f9f-42aa-a5c2-df395d7c9495
ms.openlocfilehash: 1eb1267ae0b08d558d5afc41d03270917473a669
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900912"
---
# <a name="streaming-provider-wcf-data-services"></a>Потоковый поставщик (службы WCF Data Services)

Служба данных может обеспечивать доступ к данным больших двоичных объектов. Эти двоичные данные могут представлять видео- и аудиопотоки, изображения, файлы документов или двоичные данные медиаресурсов других типов. Когда сущность в модели данных включает одно или несколько двоичных свойств, служба данных возвращает двоичные данные в кодировке base-64 в записи в канале ответа. Поскольку загрузка и сериализация больших двоичных данных подобным образом может повлиять на производительность, Open Data Protocol (OData) определяет механизм извлечения двоичных данных независимо от сущности, к которой он принадлежит. Это достигается отделением двоичных данных от сущности с последующим разделением их на один или несколько потоков данных.

- Медиаресурсы — это двоичные данные, относящиеся к сущности, такие как видео, аудио, изображения, а также потоки медиаресурсов других типов.

- Запись медиассылки — это сущность, содержащая ссылку на соответствующий поток медиаресурса.

С помощью WCF Data Services вы определяете поток двоичных ресурсов, реализуя поставщик потоковых данных. Реализация поставщика потоковой передачи предоставляет службе данных поток ресурсов мультимедиа, связанный с определенной сущностью в качестве объекта <xref:System.IO.Stream>. Эта реализация позволяет службе данных принимать и возвращать медиаресурсы по протоколу HTTP в виде потоков двоичных данных с указанным типом MIME.

Настройка службы данных для поддержки потоков двоичных данных состоит из следующих этапов.

1. Определите одну или несколько сущностей в модели данных как медиассылки. Эти сущности не должны содержать двоичные данные, предназначенные для преобразования в поток. Любые двоичные свойства сущности всегда возвращаются в записи в виде кодировки base-64.

2. Реализует интерфейс T:System.Data.Services.Providers.IDataServiceStreamProvider.

3. Определите службу данных, использующую интерфейс <xref:System.IServiceProvider>. Для доступа к реализации поставщика потоковых данных в службе данных используется реализация <xref:System.IServiceProvider.GetService%2A>. Этот метод возвращает соответствующую реализацию потокового поставщика.

4. Разрешите большие потоки сообщений в настройке веб-приложения.

5. Включите доступ к двоичным ресурсам на сервере или в источнике данных.

Примеры в этом разделе основаны на образце службы Photo Streaming, которая подробно обсуждается в [серии поставщиков потоковой передачи служб данных: реализация поставщика потоковой передачи (часть 1)](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-implementing-a-streaming-provider-part-1). Исходный код для образца службы данных для передачи фотографий доступен на сайте [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample).

## <a name="defining-a-media-link-entry-in-the-data-model"></a>Определение медиассылки в модели данных

Поставщик источника данных устанавливает способ, которым сущность определяется как медиассылка в модели данных.

**Поставщик Entity Framework**

Чтобы указать, что запись является медиассылкой, добавьте атрибут `HasStream` к определению типа сущности в концептуальной модели, как в следующем примере:

[!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]

Необходимо также добавить пространство имен `xmlns:m=http://schemas.microsoft.com/ado/2007/08/dataservices/metadata` либо в сущность, либо в корень EDMX- или CSDL-файла, определяющего модель данных.

Пример службы данных, использующей поставщик Entity Framework и предоставляющий ресурс мультимедиа, см. в [серии поставщиков потоковой передачи служб данных. Реализация поставщика потоковой передачи (часть 1)](https://docs.microsoft.com/archive/blogs/astoriateam/data-services-streaming-provider-series-implementing-a-streaming-provider-part-1).

**Поставщик отражений**

Чтобы указать, что сущность является медиассылкой, добавьте <xref:System.Data.Services.Common.HasStreamAttribute> к классу, определяющему тип сущности в поставщике отражения.

**Пользовательский поставщик службы данных**

При использовании специализированных поставщиков службы данных необходимо реализовать интерфейс <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>, чтобы определить метаданные для службы данных. Дополнительные сведения см. в разделе [пользовательские поставщики служб данных](custom-data-service-providers-wcf-data-services.md). Необходимо указать, что двоичный поток ресурса принадлежит к типу <xref:System.Data.Services.Providers.ResourceType>. Для этого свойству <xref:System.Data.Services.Providers.ResourceType.IsMediaLinkEntry%2A> задается значение `true` применительно к типу <xref:System.Data.Services.Providers.ResourceType>, представляющему тип сущности, которая является записью медиассылки.

## <a name="implementing-the-idataservicestreamprovider-interface"></a>Реализация интерфейса IDataServiceStreamProvider

Для создания потоковой службы данных, которая поддерживает двоичные потоки данных, необходимо реализовать интерфейс <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Эта реализация позволяет службе данных возвращать клиенту двоичные данные в виде потока и получать двоичные данные в виде потока от клиента. В службе данных экземпляр этого интерфейса создается каждый раз, когда возникает необходимость получить доступ к двоичным данным как к потоку. Интерфейс <xref:System.Data.Services.Providers.IDataServiceStreamProvider> определяет следующие члены.

|Имя элемента|Описание|
|-----------------|-----------------|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>|Этот метод вызывается службой данных для удаления соответствующего медиаресурса при удалении относящейся к нему медиассылки. При реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> этот метод содержит код для удаления медиаресурса, связанного с поставляемой медиассылкой.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>|Этот метод вызывается службой данных для возвращения медиаресурса в виде потока. При реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> этот метод содержит код, создающий поток, используемый службой данных для возвращения медиаресурса, связанного с предоставленной медиассылкой.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStreamUri%2A>|Этот метод вызывается службой данных для возвращения URI, используемого для запроса медиаресурса для медиассылки. Это значение используется для создания атрибута `src` в элементе содержимого медиассылки, используемого также для запроса потока данных. Если этот метод возвращает `null`, служба данных определяет URI автоматически. Этот метод следует использовать, если есть необходимость предоставить клиентам прямой доступ к двоичным данным без использования потокового поставщика.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamContentType%2A>|Этот метод вызывается службой данных для возвращения значения Content-Type медиаресурса, связанного с указанной медиассылкой.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamETag%2A>|Этот метод вызывается службой данных для возвращения eTag потока данных, связанного с указанной сущностью. Этот метод используется для управления параллелизмом в двоичных данных. Когда этот метод возвращает значение null, служба данных не отслеживает параллелизм.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>|Этот метод вызывается службой данных для получения потока, используемого при принятии потока, отправляемого от клиента. При реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> необходимо возвращать поток с возможностью записи, в который служба данных записывает принимаемые потоковые данные.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.ResolveType%2A>|Возвращает имя типа с именем пространства имен, представляющее тип, который среда выполнения службы данных должна создать для медиассылки, связанной с потоком данных для вставляемого медиаресурса.|

## <a name="creating-the-streaming-data-service"></a>Создание потоковой службы данных

Чтобы предоставить среде выполнения WCF Data Services доступ к реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, создаваемая служба данных также должна реализовывать интерфейс <xref:System.IServiceProvider>. В следующем примере показана реализация метода <xref:System.IServiceProvider.GetService%2A>, который возвращает экземпляр класса `PhotoServiceStreamProvider`, реализующего <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.

[!code-csharp[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_service/cs/photodata.svc.cs#photoservicestreamingprovider)]
[!code-vb[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_service/vb/photodata.svc.vb#photoservicestreamingprovider)]

Общие сведения о создании службы данных см. в разделе [Настройка службы данных](configuring-the-data-service-wcf-data-services.md).

## <a name="enabling-large-binary-streams-in-the-hosting-environment"></a>Включение больших двоичных потоков в среде размещения

При создании службы данных в веб-приложении ASP.NET для предоставления реализации протокола HTTP используется Windows Communication Foundation (WCF). По умолчанию WCF устанавливает для HTTP-сообщений максимальный размер в 65 КБ. Чтобы иметь возможность направлять большие потоки двоичных данных в службу данных и из нее, необходимо также настроить веб-приложение, включив возможность использования больших двоичных файлов и потоков для передачи. Для этого добавьте к элементу `<configuration />` файла Web.config приложения следующее.

> [!NOTE]
> Необходимо использовать режим передачи <xref:System.ServiceModel.TransferMode.Streamed?displayProperty=nameWithType>, чтобы обеспечить потоковую передачу двоичных данных в сообщениях запроса и ответа и не помещает их в буфер WCF.

Дополнительные сведения см. в разделе [потоковая передача сообщений](../../wcf/feature-details/streaming-message-transfer.md) и [квоты транспорта](../../wcf/feature-details/transport-quotas.md).

По умолчанию службы IIS также накладывают на размер запроса ограничение в 4 МБ. Чтобы служба данных получала больше 4 МБ при работе в службах IIS, необходимо также задать атрибут `maxRequestLength` [элемента httpRuntime (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e1f13641(v=vs.100)) в разделе конфигурации `<system.web />`, как показано в следующем примере:

## <a name="using-data-streams-in-a-client-application"></a>Использование потоков данных в клиентском приложении

Клиентская библиотека WCF Data Services позволяет получать и обновлять эти ресурсы как двоичные потоки на клиенте. Дополнительные сведения см. в разделе [Работа с двоичными данными](working-with-binary-data-wcf-data-services.md).

## <a name="considerations-for-working-with-a-streaming-provider"></a>Вопросы по работе с потоковым поставщиком

Следующие моменты следует учитывать при реализации потокового поставщика и доступе к медиаресурсам из службы данных.

- Запросы MERGE для медиаресурсов не поддерживаются. Используйте запрос PUT для изменения медиаресурса существующей сущности.

- Запрос POST не может использоваться для создания новой медиассылки. Вместо этого необходимо выдать запрос POST для создания нового медиаресурса, а служба данных создаст новую медиассылку со значениями по умолчанию. Эта новая сущность может впоследствии обновляться с помощью запросов MERGE или PUT. Также можно кэшировать сущность и вносить обновления в модуль удаления, такие как установка для свойства значения, равного заголовку Slug в запросе POST.

- После приема запроса POST служба данных вызывает метод <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> для создания медиаресурса перед вызовом <xref:System.Data.Services.IUpdatable.SaveChanges%2A> для создания медиассылки.

- Реализация <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> не должна возвращать объект <xref:System.IO.MemoryStream>. При использовании потока подобного типа будут возникать проблемы, связанные с использованием памяти, во время получения очень больших потоков данных.

- Следующие факторы следует учитывать при хранении медиаресурсов в базе данных:

  - Двоичное свойство, являющееся медиаресурсом, не должно включаться в модель данных. Все свойства, предоставляемые в модели данных, возвращаются в записи в канале ответа.

  - Чтобы улучшить производительность при работе с большим двоичным потоком, рекомендуется создать пользовательский класс потока для хранения двоичных данных в базе данных. Этот класс возвращается посредством реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> и отправляет двоичные данные в базу данных в виде фрагментов. Для SQL Server базы данных рекомендуется использовать FILESTREAM для потоковой передачи данных в базу данных, если двоичные данные больше 1 МБ.

  - Убедитесь в том, что база данных предусматривает хранение больших двоичных потоков, получаемых используемой службой данных.

  - Когда клиент отправляет запрос POST для вставки медиассылки и медиаресурса в одном запросе, для получения потока вызывается метод <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> перед тем, как служба данных вставит новую сущность в базу данных. Реализация потокового поставщика должна уметь работать с таким поведением службы данных. Рассмотрите возможность использования отдельной таблицы данных для хранения двоичных данных или хранения потока данных в файле до вставки сущности в базу данных.

- При реализации методов <xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>, <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A> или <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> необходимо использовать значения eTag и Content-Type, предоставляемые в качестве параметров метода. Не устанавливайте заголовки eTag или Content-Type в реализации поставщика <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.

- По умолчанию клиент отправляет большие двоичные потоки, используя фрагментированный HTTP Transfer-Encoding. Поскольку ASP.NET Development Server не поддерживает такой тип кодирования, этот веб-сервер нельзя использовать для размещения службы потоковой передачи данных, которая должна принимать большие двоичные потоки. Дополнительные сведения о ASP.NET Development Server см. [в разделе веб-серверы в Visual Studio для веб-проектов ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

<a name="versioning"></a>

## <a name="versioning-requirements"></a>Требования к управлению версиями

Поставщик потоковой передачи имеет следующие требования к версии протокола OData:

- Поставщик потоковой передачи требует, чтобы служба данных поддерживала версию 2,0 протокола OData и более поздних версий.

Дополнительные сведения см. в разделе [Управление версиями службы данных](data-service-versioning-wcf-data-services.md).

## <a name="see-also"></a>См. также:

- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
- [Специализированные поставщики служб данных](custom-data-service-providers-wcf-data-services.md)
- [Работа с двоичными данными](working-with-binary-data-wcf-data-services.md)
