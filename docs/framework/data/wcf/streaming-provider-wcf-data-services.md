---
title: Потоковый поставщик (службы WCF Data Services)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, binary data
- streaming data provider [WCF Data Services]
- WCF Data Services, streams
ms.assetid: f0978fe4-5f9f-42aa-a5c2-df395d7c9495
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc66d4154f60e46e53de8ca72596e133dc84eb97
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="streaming-provider-wcf-data-services"></a>Потоковый поставщик (службы WCF Data Services)
Служба данных может обеспечивать доступ к данным больших двоичных объектов. Эти двоичные данные могут представлять видео- и аудиопотоки, изображения, файлы документов или двоичные данные медиаресурсов других типов. Когда сущность в модели данных включает одно или несколько двоичных свойств, служба данных возвращает двоичные данные в кодировке base-64 в записи в канале ответа. Так как загрузка и сериализация больших объемов двоичных данных, таким образом может повлиять на производительность, [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] определяет механизм получения двоичных данных независимо от сущности, к которой он принадлежит. Это достигается отделением двоичных данных от сущности с последующим разделением их на один или несколько потоков данных.  
  
-   Медиаресурсы — это двоичные данные, относящиеся к сущности, такие как видео, аудио, изображения, а также потоки медиаресурсов других типов.  
  
-   Запись медиассылки — это сущность, содержащая ссылку на соответствующий поток медиаресурса.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет определить двоичный поток ресурса путем определения поставщика потоковых данных. Реализация потокового поставщика предоставляет службе данных с медиаресурса, связанный с конкретной сущностью, как <xref:System.IO.Stream> объект. Эта реализация позволяет службе данных принимать и возвращать медиаресурсы по протоколу HTTP в виде потоков двоичных данных с указанным типом MIME.  
  
 Настройка службы данных для поддержки потоков двоичных данных состоит из следующих этапов.  
  
1.  Определите одну или несколько сущностей в модели данных как медиассылки. Эти сущности не должны содержать двоичные данные, предназначенные для преобразования в поток. Любые двоичные свойства сущности всегда возвращаются в записи в виде кодировки base-64.  
  
2.  Реализует интерфейс T:System.Data.Services.Providers.IDataServiceStreamProvider.  
  
3.  Определите службу данных, использующую интерфейс <xref:System.IServiceProvider>. Для доступа к реализации поставщика потоковых данных в службе данных используется реализация <xref:System.IServiceProvider.GetService%2A>. Этот метод возвращает соответствующую реализацию потокового поставщика.  
  
4.  Разрешите большие потоки сообщений в настройке веб-приложения.  
  
5.  Включите доступ к двоичным ресурсам на сервере или в источнике данных.  
  
 Примеры в этом разделе основаны на образце потоковой службы хранения фотографий, которая подробно обсуждается в записи блога [рядов поставщика потоковой передачи: реализация потокового поставщика (часть 1)](http://go.microsoft.com/fwlink/?LinkID=198989). Исходный код для этого образца службы можно найти в [страницы данных образец потоковой службы](http://go.microsoft.com/fwlink/?LinkID=198988) в коллекции кода MSDN.  
  
## <a name="defining-a-media-link-entry-in-the-data-model"></a>Определение медиассылки в модели данных  
 Поставщик источника данных устанавливает способ, которым сущность определяется как медиассылка в модели данных.  
  
 **Поставщик Entity Framework**  
 Чтобы указать, что запись является медиассылкой, добавьте атрибут `HasStream` к определению типа сущности в концептуальной модели, как в следующем примере:  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria photo streaming service/xml/photodata.edmx#hasstream)]  
  
 Необходимо также добавить пространство имен `xmlns:m=http://schemas.microsoft.com/ado/2007/08/dataservices/metadata` либо в сущность, либо в корень EDMX- или CSDL-файла, определяющего модель данных.  
  
 Пример службы данных, которая использует [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] поставщика и предоставляет доступ к медиаресурсу, см. в публикации [рядов поставщика потоковой передачи: реализация потокового поставщика (часть 1)](http://go.microsoft.com/fwlink/?LinkID=198989).  
  
 **Поставщик отражений**  
 Чтобы указать, что сущность является медиассылкой, добавьте <xref:System.Data.Services.Common.HasStreamAttribute> к классу, определяющему тип сущности в поставщике отражения.  
  
 **Пользовательским поставщиком службы данных**  
 При использовании специализированных поставщиков службы данных необходимо реализовать интерфейс <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>, чтобы определить метаданные для службы данных. Дополнительные сведения см. в разделе [настраиваемых поставщиков данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md). Необходимо указать, что двоичный поток ресурса принадлежит к типу <xref:System.Data.Services.Providers.ResourceType>. Для этого свойству <xref:System.Data.Services.Providers.ResourceType.IsMediaLinkEntry%2A> задается значение `true` применительно к типу <xref:System.Data.Services.Providers.ResourceType>, представляющему тип сущности, которая является записью медиассылки.  
  
## <a name="implementing-the-idataservicestreamprovider-interface"></a>Реализация интерфейса IDataServiceStreamProvider  
 Для создания потоковой службы данных, которая поддерживает двоичные потоки данных, необходимо реализовать интерфейс <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Эта реализация позволяет службе данных возвращать клиенту двоичные данные в виде потока и получать двоичные данные в виде потока от клиента. В службе данных экземпляр этого интерфейса создается каждый раз, когда возникает необходимость получить доступ к двоичным данным как к потоку. Интерфейс <xref:System.Data.Services.Providers.IDataServiceStreamProvider> определяет следующие члены.  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>|Этот метод вызывается службой данных для удаления соответствующего медиаресурса при удалении относящейся к нему медиассылки. При реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> этот метод содержит код для удаления медиаресурса, связанного с поставляемой медиассылкой.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>|Этот метод вызывается службой данных для возвращения медиаресурса в виде потока. При реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> этот метод содержит код, создающий поток, используемый службой данных для возвращения медиаресурса, связанного с предоставленной медиассылкой.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStreamUri%2A>|Этот метод вызывается службой данных для возвращения URI, используемого для запроса медиаресурса для медиассылки. Это значение используется для создания атрибута `src` в элементе содержимого медиассылки, используемого также для запроса потока данных. Если этот метод возвращает `null`, служба данных определяет URI автоматически. Этот метод следует использовать, если есть необходимость предоставить клиентам прямой доступ к двоичным данным без использования потокового поставщика.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamContentType%2A>|Этот метод вызывается службой данных для возвращения значения Content-Type медиаресурса, связанного с указанной медиассылкой.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamETag%2A>|Этот метод вызывается службой данных для возвращения eTag потока данных, связанного с указанной сущностью. Этот метод используется для управления параллелизмом в двоичных данных. Когда этот метод возвращает значение null, служба данных не отслеживает параллелизм.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>|Этот метод вызывается службой данных для получения потока, используемого при принятии потока, отправляемого от клиента. При реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> необходимо возвращать поток с возможностью записи, в который служба данных записывает принимаемые потоковые данные.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.ResolveType%2A>|Возвращает имя типа с именем пространства имен, представляющее тип, который среда выполнения службы данных должна создать для медиассылки, связанной с потоком данных для вставляемого медиаресурса.|  
  
## <a name="creating-the-streaming-data-service"></a>Создание потоковой службы данных  
 Для предоставления среде выполнения [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] доступа к реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider> необходимо, чтобы создаваемая служба данных реализовывала также интерфейс <xref:System.IServiceProvider>. В следующем примере показана реализация метода <xref:System.IServiceProvider.GetService%2A>, который возвращает экземпляр класса `PhotoServiceStreamProvider`, реализующего <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.  
  
 [!code-csharp[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming service/cs/photodata.svc.cs#photoservicestreamingprovider)]
 [!code-vb[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming service/vb/photodata.svc.vb#photoservicestreamingprovider)]  
  
 Общие сведения о создании службы данных см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
## <a name="enabling-large-binary-streams-in-the-hosting-environment"></a>Включение больших двоичных потоков в среде размещения  
 При создании службы данных в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-приложение, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] используется, чтобы предоставить реализацию протокола HTTP. По умолчанию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ограничивает размер сообщений HTTP только 65 тысяч байт. Чтобы иметь возможность направлять большие потоки двоичных данных в службу данных и из нее, необходимо также настроить веб-приложение, включив возможность использования больших двоичных файлов и потоков для передачи. Для этого добавьте к элементу `<configuration />` файла Web.config приложения следующее.  
  
  
  
> [!NOTE]
>  Необходимо использовать режим передачи <xref:System.ServiceModel.TransferMode.Streamed?displayProperty=nameWithType>, чтобы обеспечить для двоичных данных запроса и ответа потоковую передачу и отсутствие буферизации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Дополнительные сведения см. в разделе [потоковая передача сообщений](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md) и [квоты транспорта](../../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 По умолчанию службы IIS также накладывают на размер запроса ограничение в 4 МБ. Чтобы включить службу данных для получения потоков, размер которых превышает 4 МБ, при выполнении с IIS, необходимо также задать `maxRequestLength` атрибут [httpRuntime (схема параметров ASP.NET) элемент](http://msdn.microsoft.com/library/e9b81350-8aaf-47cc-9843-5f7d0c59f369) в `<system.web />` раздел конфигурации, как показано в следующем примере:  
  
  
  
## <a name="using-data-streams-in-a-client-application"></a>Использование потоков данных в клиентском приложении  
 Клиентская библиотека [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет и получать и обновлять эти предоставленные ресурсы в виде двоичных потоков на клиенте. Дополнительные сведения см. в разделе [работа с двоичными данными](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md).  
  
## <a name="considerations-for-working-with-a-streaming-provider"></a>Вопросы по работе с потоковым поставщиком  
 Следующие моменты следует учитывать при реализации потокового поставщика и доступе к медиаресурсам из службы данных.  
  
-   Запросы MERGE для медиаресурсов не поддерживаются. Используйте запрос PUT для изменения медиаресурса существующей сущности.  
  
-   Запрос POST не может использоваться для создания новой медиассылки. Вместо этого необходимо выдать запрос POST для создания нового медиаресурса, а служба данных создаст новую медиассылку со значениями по умолчанию. Эта новая сущность может впоследствии обновляться с помощью запросов MERGE или PUT. Также можно кэшировать сущность и вносить обновления в модуль удаления, такие как установка для свойства значения, равного заголовку Slug в запросе POST.  
  
-   После приема запроса POST служба данных вызывает метод <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> для создания медиаресурса перед вызовом <xref:System.Data.Services.IUpdatable.SaveChanges%2A> для создания медиассылки.  
  
-   Реализация <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> не должна возвращать объект <xref:System.IO.MemoryStream>. При использовании потока подобного типа будут возникать проблемы, связанные с использованием памяти, во время получения очень больших потоков данных.  
  
-   Следующие факторы следует учитывать при хранении медиаресурсов в базе данных:  
  
    -   Двоичное свойство, являющееся медиаресурсом, не должно включаться в модель данных. Все свойства, предоставляемые в модели данных, возвращаются в записи в канале ответа.  
  
    -   Чтобы улучшить производительность при работе с большим двоичным потоком, рекомендуется создать пользовательский класс потока для хранения двоичных данных в базе данных. Этот класс возвращается посредством реализации <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> и отправляет двоичные данные в базу данных в виде фрагментов. Для базы данных SQL Server рекомендуется использовать FILESTREAM для потоковой передачи данных в базу данных, если двоичных данных превышает 1 МБ.  
  
    -   Убедитесь в том, что база данных предусматривает хранение больших двоичных потоков, получаемых используемой службой данных.  
  
    -   Когда клиент отправляет запрос POST для вставки медиассылки и медиаресурса в одном запросе, для получения потока вызывается метод <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> перед тем, как служба данных вставит новую сущность в базу данных. Реализация потокового поставщика должна уметь работать с таким поведением службы данных. Рассмотрите возможность использования отдельной таблицы данных для хранения двоичных данных или хранения потока данных в файле до вставки сущности в базу данных.  
  
-   При реализации методов <xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>, <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A> или <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> необходимо использовать значения eTag и Content-Type, предоставляемые в качестве параметров метода. Не устанавливайте заголовки eTag или Content-Type в реализации поставщика <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.  
  
-   По умолчанию клиент отправляет большие двоичные потоки, используя фрагментированный HTTP Transfer-Encoding. Поскольку [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server не поддерживает данный тип кодировки, нельзя использовать этот веб-сервер для размещения потоковой службы данных, предназначенной для приема больших двоичных потоков. Дополнительные сведения о [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server. в разделе [веб-серверов в Visual Studio для веб-проектов ASP.NET](http://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
<a name="versioning"></a>   
## <a name="versioning-requirements"></a>Требования к управлению версиями  
 Потоковый поставщик предъявляет следующие требования к управлению версиями протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
-   Потоковый поставщик требует, чтобы служба данных поддерживала версию 2.0 протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] и последующие версии.  
  
 Дополнительные сведения см. в разделе [управление версиями службы данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Специализированные поставщики служб данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)  
 [Работа с двоичными данными](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)
