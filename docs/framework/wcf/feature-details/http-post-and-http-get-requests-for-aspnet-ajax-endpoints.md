---
title: "Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 340f06c760ec4af6427343578790a8dad2d5dd62
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет создать службу, предоставляющую конечную точку с поддержкой ASP.NET AJAX, которую можно вызвать из кода JavaScript на веб-сайте клиента. Основные процедуры для создания таких служб, рассматривается в [как: использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) и [как: Добавление ASP.NET AJAX конфигурации конечной точки без с помощью](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 ASP.NET AJAX поддерживает операции, которые используют команды HTTP POST и HTTP GET (команда HTTP POST задана по умолчанию). При создании операции, не имеющей побочных эффектов и возвращающей данные, которые меняются очень редко или не меняются никогда, необходимо вместо команды по умолчанию использовать HTTP GET. Результаты операций GET можно кэшировать, чтобы представить несколько вызовов одной операции в виде одного запроса службе. Кэширование не осуществляется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], но может происходить на любом уровне (в браузере пользователя, на прокси-сервере и других уровнях). Кэширование обладает значительными преимуществами, если необходимо повысить производительность службы, но оказывается неприемлемым, если данные часто изменяются или операция выполняет какие-либо действия.  
  
 Например, при создании службы для управления музыкальной библиотекой пользователя операция, осуществляющая поиск исполнителя по названию альбома, должна использовать команду GET, а операция, добавляющая альбом в личную коллекцию пользователя - команду POST.  
  
 Для управления временем существования кэша следует использовать тип <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Например, при создании службы, возвращающей ежечасно обновляемые прогнозы погоды, логично использовать команду GET, ограничив длительность кэширования одним часом (или меньшим промежутком времени), чтобы пользователи службы не имели доступа к устаревшим данным.  
  
 При работе со службами со страницы ASP.NET AJAX, которые используют средство управления диспетчера скриптов, не имеет значения, использует ли операция команду GET или POST, так как механизм диспетчера скриптов обеспечивает выдачу правильного типа запроса.  
  
 Операции HTTP GET используют любые входные параметры, поддерживаемые операциями POST, включая сложные типы контрактов данных. Однако в большинстве случаев в операциях GET не рекомендуется использовать слишком много параметров или слишком сложные параметры, так как это снижает эффективность кэширования.  
  
 В этом разделе также объясняется, как выбрать между командами GET и POST, добавив в соответствующие операции в контракте службы атрибуты <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>. Другие действия (по реализации, настройке и размещению службы), необходимые для работы со службой, аналогичны выполняемым для любой службы ASP.NET AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Операция, помеченная атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>, всегда использует запрос GET. Операция, помеченная атрибутом <xref:System.ServiceModel.Web.WebInvokeAttribute> или не помеченная ни одним из двух атрибутов, использует запрос POST. Атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> позволяет использовать другие HTTP-команды (кроме GET и POST, например PUT и DELETE) через свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. Однако эти команды не поддерживаются ASP.NET AJAX. Если планируется использовать службу со страниц ASP.NET с помощью средства управления диспетчера скриптов, применять свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> не следует.  
  
 Для переключения на получение рабочий пример см. в разделе [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца.  
  
 Пример, в котором используется POST, в разделе [AJAX службы с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) образца.  
  
### <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Создание службы WCF, отвечающей на запросы HTTP GET или HTTP POST  
  
1.  Определите контракт базовой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью интерфейса, помеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Добавьте атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, чтобы указать, что операция должна отвечать на запросы HTTP GET. Также можно использовать атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>, чтобы явно задать HTTP POST, либо не указывать атрибут, и в этом случае по умолчанию будет использоваться HTTP POST.  
  
    ```  
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  Реализуйте контракт службы `IMusicService` с помощью класса `MusicService`.  
  
    ```  
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3.  Создайте в приложении новый файл с именем "service" и расширением .svc. Измените этот файл, добавив соответствующие [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директив сведения о службе. Указать, что <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> будет использоваться в [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директиву, чтобы автоматически настроить конечную точку ASP.NET AJAX.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
### <a name="to-call-the-service"></a>Вызов службы  
  
1.  Протестировать операции GET службы можно без кода клиента с помощью браузера. Например, если служба настроена по адресу "http://example.com/service.svc", то ввод "http://example.com/service.svc/LookUpArtist?album=SomeAlbum" в адресной строке браузера вызывает службу, загружает или отображает ответ.  
  
2.  Службы с операциями GET можно использовать так же, как и любые другие службы ASP.NET AJAX, т. е. введя URL-адрес службы в коллекцию скриптов средства управления диспетчера скриптов ASP.NET AJAX. Пример см. в разделе [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
## <a name="see-also"></a>См. также  
 [Создание службы WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Как: миграция с поддержкой AJAX веб-служб ASP.NET в WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
