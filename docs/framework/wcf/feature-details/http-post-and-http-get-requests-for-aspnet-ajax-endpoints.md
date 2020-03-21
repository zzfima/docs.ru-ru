---
title: Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 0f7a221d1fd14b4a978683f008858e35cbd2df19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184754"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX

Фонд связи Windows (WCF) позволяет создать сервис, который предоставляет ASP.NET топовой с поддержкой AJAX, которая может быть вызвана из JavaScript на веб-сайте клиента. Основные процедуры создания таких сервисов обсуждаются в программе [«Как: используйте конфигурацию для добавления ASP.NET точечной точки AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) и [как: добавить ASP.NET конечную точку AJAX без использования конфигурации.](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
  
 ASP.NET AJAX поддерживает операции, которые используют команды HTTP POST и HTTP GET (команда HTTP POST задана по умолчанию). При создании операции, не имеющей побочных эффектов и возвращающей данные, которые меняются очень редко или не меняются никогда, необходимо вместо команды по умолчанию использовать HTTP GET. Результаты операций GET можно кэшировать, чтобы представить несколько вызовов одной операции в виде одного запроса службе. Кэширование не выполняется WCF, но может происходить на любом уровне (в браузере пользователя, на прокси-сервере и на других уровнях). Кэширование выгодно, если вы хотите повысить производительность обслуживания, но может быть неприемлемым, если данные часто изменяются или если операция выполняет некоторые действия.  
  
 Например, при создании службы для управления музыкальной библиотекой пользователя операция, осуществляющая поиск исполнителя по названию альбома, должна использовать команду GET, а операция, добавляющая альбом в личную коллекцию пользователя - команду POST.  
  
 Для управления временем существования кэша следует использовать тип <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Например, при создании службы, возвращающей ежечасно обновляемые прогнозы погоды, логично использовать команду GET, ограничив длительность кэширования одним часом (или меньшим промежутком времени), чтобы пользователи службы не имели доступа к устаревшим данным.  
  
 При работе со службами со страницы ASP.NET AJAX, которые используют средство управления диспетчера скриптов, не имеет значения, использует ли операция команду GET или POST, так как механизм диспетчера скриптов обеспечивает выдачу правильного типа запроса.  
  
 Операции HTTP GET используют любые входные параметры, поддерживаемые операциями POST, включая сложные типы контрактов данных. Однако в большинстве случаев в операциях GET не рекомендуется использовать слишком много параметров или слишком сложные параметры, так как это снижает эффективность кэширования.  
  
 В этом разделе также объясняется, как выбрать между командами GET и POST, добавив в соответствующие операции в контракте службы атрибуты <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>. Другие шаги (для реализации, настройки и размещения службы), которые необходимы для запуска службы, аналогичны тем, которые используются любым ASP.NET службой AJAX в WCF.  
  
 Операция, помеченная атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>, всегда использует запрос GET. Операция, помеченная атрибутом <xref:System.ServiceModel.Web.WebInvokeAttribute> или не помеченная ни одним из двух атрибутов, использует запрос POST. Атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> позволяет использовать другие HTTP-команды (кроме GET и POST, например PUT и DELETE) через свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. Однако эти команды не поддерживаются ASP.NET AJAX. Если планируется использовать службу со страниц ASP.NET с помощью средства управления диспетчера скриптов, применять свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> не следует.  
  
 На примере перехода на GET можно ознакомиться на примере [основной службы AJAX.](../../../../docs/framework/wcf/samples/basic-ajax-service.md)  
  
 Для примера, который использует POST, см. [службу AJAX С использованием образца HTTP POST.](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Создание службы WCF, отвечающей на запросы HTTP GET или HTTP POST
  
1. Определите базовый контракт службы WCF <xref:System.ServiceModel.ServiceContractAttribute> с интерфейсом, отмеченным атрибутом. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Добавьте атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, чтобы указать, что операция должна отвечать на запросы HTTP GET. Также можно использовать атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>, чтобы явно задать HTTP POST, либо не указывать атрибут, и в этом случае по умолчанию будет использоваться HTTP POST.
  
    ```csharp
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
  
2. Реализуйте контракт службы `IMusicService` с помощью класса `MusicService`.
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. Создайте в приложении новый файл с именем "service" и расширением .svc. Отобразите этот файл, добавив соответствующую [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивную информацию ServiceHost для службы. Укажите, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> что это должно использоваться в директиве [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) для автоматической настройки ASP.NET конечную точку AJAX.  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>Вызов службы  
  
1. Протестировать операции GET службы можно без кода клиента с помощью браузера. Например, если служба настроена `http://example.com/service.svc` по адресу, `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` то ввод в строку адреса браузера вызывает службу и вызывает загрузку или отображение ответа.
  
2. Службы с операциями GET можно использовать так же, как и любые другие службы ASP.NET AJAX, т. е. введя URL-адрес службы в коллекцию скриптов средства управления диспетчера скриптов ASP.NET AJAX. Например, [см.](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
  
## <a name="see-also"></a>См. также раздел

- [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
