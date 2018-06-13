---
title: Разработка и развертывание служб WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: ca0f78239e6e259ec5bd75e9f93af5c3a4b7adf1
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805451"
---
# <a name="developing-and-deploying-wcf-data-services"></a>Разработка и развертывание служб WCF Data Services
Этот раздел содержит сведения о разработке и развертывании [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Дополнительные сведения о [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], в разделе [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) и [Обзор](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).  
  
## <a name="developing-wcf-data-services"></a>Разработка служб данных WCF  
 При использовании [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для создания службы данных, поддерживающей [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], необходимо во время разработки выполнить приведенные ниже основные задачи.  
  
1.  **Определение модели данных**  
  
     Службы[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживают различные поставщики служб данных, позволяющие определить модель данных на основе данных из различных источников данных, от реляционных баз данных до данных с поздним связыванием. Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
2.  **Создание службы данных**  
  
     Самая базовая служба данных предоставляет класс, производный от класса <xref:System.Data.Services.DataService%601> , с типом `T` , представляющим имя контейнера сущностей, квалифицированное пространством имен. Дополнительные сведения см. в разделе [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Настройка службы данных**  
  
     По умолчанию службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] запрещают доступ к ресурсам, предоставляемым контейнером сущностей. Интерфейс <xref:System.Data.Services.DataServiceConfiguration> позволяет настроить доступ к ресурсам и операциям службы, задать поддерживаемую версию [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], а также определить другие особенности поведения службы, такие как использование пакетирования или максимальное количество сущностей, которые могут быть возвращены в одном канале ответа. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 В этом разделе описывается в первую очередь разработка и развертывание служб данных с помощью Visual Studio. Сведения о гибких возможностях [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] по предоставлению данных в виде каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] см. в разделе [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
### <a name="choosing-a-development-web-server"></a>Выбор веб-сервера развертывания  
 При разработке службы данных WCF в качестве [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложения или [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-сайта с помощью Visual Studio, имеется выбор из веб-серверов, на котором работает служба данных во время разработки. Следующие веб-серверы интегрируются с Visual Studio, чтобы упростить тестирование и отладку служб данных на локальном компьютере.  
  
1.  **Локальный сервер служб IIS**  
  
     При создании службы данных, которая является приложением [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или веб-узлом [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , работающим на базе служб IIS, рекомендуется разрабатывать и тестировать службу данных с помощью IIS на локальном компьютере. Запуск службы данных в IIS упрощает трассировку HTTP-запросов во время отладки. Это также позволяет заранее определить необходимые права, которые требуются службам IIS для доступа к файлам, базам данных и другим ресурсам для службы данных. Для запуска службы данных на сервере IIS, необходимо позволяет убедиться, что службы IIS и Windows Communication Foundation (WCF) установлена и правильно настроен и предоставить доступ к учетным записям IIS к файловой системе и базам данных. Для получения дополнительной информации см. [Практическое руководство. Разработка службы данных WCF Data Service, работающей на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
    > [!NOTE]
    >  Необходимо запустить Visual Studio с правами администратора, чтобы позволить среде разработки настроить локальный сервер IIS.  
  
2.  **Сервер разработки Visual Studio**  
  
     Visual Studio включает встроенный веб-сервер Visual Studio Development Server, который является веб-сервер по умолчанию [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проектов. Этот веб-сервер предназначен для запуска проектов [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] на локальном компьютере во время разработки. [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) показано, как создать службу данных, которая выполняется в Visual Studio Development Server.  
  
     При разработке службы данных с помощью Visual Studio Development Server необходимо учитывать следующие ограничения.  
  
    -   Доступ к этому серверу возможен только с локального компьютера.  
  
    -   Этот сервер прослушивает `localhost` и указанный порт, отличный от порта 80, который по умолчанию настроен для HTTP-сообщений. Дополнительные сведения см. в разделе [Веб-серверы в Visual Studio для веб-проектов ASP.NET](http://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
    -   На этом сервере служба данных работает в контексте текущей учетной записи пользователя. Например при запуске пользователя уровня администратора служба данных, работающая в Visual Studio Development Server будет иметь прав администратора. Это может обеспечить службе данных доступ к ресурсам, для которых у нее не будет прав после развертывания на сервере служб IIS.  
  
    -   На этом сервере отсутствуют дополнительные возможности служб IIS, такие как проверка подлинности.  
  
    -   Этот сервер не может обрабатывать потоки HTTP частями, которые по умолчанию отправляются клиентом [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] при обращении к большим объемам двоичных данных из службы данных. Дополнительные сведения см. в разделе [потокового поставщика](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
    -   У этого сервера есть проблемы с обработкой символа точки (`.`) в URL-адресах, хотя этот символ и поддерживается [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в значениях ключа.  
  
    > [!TIP]
    >  Даже при использовании Visual Studio Development Server для тестирования служб данных во время разработки вы следует повторно их протестировать после развертывания на веб-сервере, на котором работает IIS.  
  
3.  **Среда разработки Microsoft Azure**  
  
     Windows Azure Tools для Visual Studio входит интегрированный набор средств для разработки служб Windows Azure в Visual Studio. С помощью этих средств можно разрабатывать службы данных, которые могут развертываться на Microsoft Azure, а также тестировать службу данных на локальном компьютере перед развертыванием. Эти средства можно используйте при разработке службы данных, работающей на платформе Windows Azure с помощью Visual Studio. Вы можете загрузить инструменты Windows Azure для Visual Studio из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=201848). Дополнительные сведения о разработке службы данных, которая работает в Windows Azure см. в публикации [Deploying an OData Service в Windows Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="development-tips"></a>Советы по разработке  
 При разработке службы данных необходимо учитывать следующее:  
  
-   Определите требования по безопасности к службе данных, если планируется проверять подлинность пользователей или ограничивать доступ определенным пользователям. Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
-   Программа проверки HTTP может быть очень полезной при развертывании службы данных, позволяя проверять содержимое сообщений запросов и ответов. Любой планировщик сетевых пакетов, способный отображать необработанные пакеты, можно использовать для проверки HTTP-запросов к службе данных и ответов от нее.  
  
-   При отладке службы данных, возможно, потребуется получать от службы данных больше сведений об ошибках, чем при нормальной работе. Дополнительные сведения об ошибках можно получить из службы данных, установив свойство <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> в <xref:System.Data.Services.DataServiceConfiguration> значение `true` , а свойство <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> атрибута <xref:System.ServiceModel.Description.ServiceDebugBehavior> класса службы данных — в значение `true`. Дополнительные сведения см. в публикации [Debugging WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=201868). Можно также включить трассировку в WCF для просмотра исключений, вызываемых уровнем сообщений HTTP. Для получения дополнительной информации см. [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   Служба данных обычно разрабатывается как [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проект приложения, но можно также создать службу данных как [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта веб-сайта в Visual Studio. Сведения о различиях между двумя типами проектов см. в разделе [NIB: проекты веб-приложений и проектами веб-сайтов в Visual Studio](http://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5).  
  
-   При создании службы данных с помощью **Добавление нового элемента** диалоговое окно в Visual Studio, службы данных управляется [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] в службах IIS. Несмотря на то что [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и IIS используются для размещения службы данных по умолчанию, поддерживаются и другие варианты размещения. Дополнительные сведения см. в разделе [размещение служб данных](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).  
  
## <a name="deploying-wcf-data-services"></a>Развертывание служб данных WCF  
 Службы данных WCF обеспечивают гибкость в выборе процесса, в котором будет размещаться служба данных. Visual Studio можно использовать для развертывания служб данных на следующих платформах:  
  
-   **Веб-сервер, размещенный в службах IIS**  
  
     Если служба данных разрабатывается как проект [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , то его можно развернуть на веб-сервере IIS с помощью стандартной процедуры развертывания [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  Visual Studio обеспечивает следующие технологии развертывания для [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в зависимости от типа объекта [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] службой данных, который выполняется развертывание проекта.  
  
    -   **Технологии развертывания для веб-приложений ASP.NET**  
  
        -   [Пакет веб-развертывания](http://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)  
  
        -   [Публикация одним щелчком](http://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)  
  
    -   **Технологии развертывания для веб-узлов ASP.NET**  
  
        -   [Средство копирования веб-узлов](http://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)  
  
        -   [Средство публикации веб-узлов](http://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)  
  
        -   [XCopy](http://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)  
  
     Дополнительные сведения о вариантах развертывания [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложения, в разделе [Обзор веб-развертывания Visual Studio и ASP.NET](http://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).  
  
    > [!TIP]
    >  Прежде чем пытаться выполнить развертывание службы данных в IIS, обязательно протестируйте развертывание на веб-сервере, где работают службы IIS. Для получения дополнительной информации см. [Практическое руководство. Разработка службы данных WCF Data Service, работающей на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
-   **Microsoft Azure**  
  
     Службы данных можно развернуть в Windows Azure с помощью средств Windows Azure для Visual Studio. Вы можете загрузить инструменты Windows Azure для Visual Studio из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=201848). Дополнительные сведения о развертывании службы данных в Windows Azure см. в публикации [Deploying an OData Service в Windows Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="deployment-considerations"></a>Требования к развертыванию  
 При разработке службы данных необходимо учитывать следующее:  
  
-   При развертывании службы данных, использующей поставщика [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] для доступа к базе данных SQL Server, можно также распространить структуры данных, данные или и то и другое. Visual Studio может автоматически создать скрипты (SQL-файлы), чтобы сделать это в целевой базе данных, и эти скрипты можно включить в пакет веб-развертывания из [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложения. Дополнительные сведения см. в разделе [NIB: Практическое: развертывание базы данных с проектом веб-приложения](http://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b). Для [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-сайта, это можно сделать помощью **мастер публикации базы данных** в Visual Studio. Для получения дополнительной информации см. [развертывание базы данных с помощью мастера публикации баз данных](http://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).   
  
-   Поскольку [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включает в себя базовую реализацию WCF, можно использовать Windows Server AppFabric для наблюдения за службами данных, развернутой на IIS под управлением Windows Server. Дополнительные сведения об использовании Windows Server AppFabric для наблюдения за службами данных см. в публикации [Tracking WCF Data Services с Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=202005).  
  
## <a name="see-also"></a>См. также  
 [Размещение служб данных](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 [Защита служб WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
