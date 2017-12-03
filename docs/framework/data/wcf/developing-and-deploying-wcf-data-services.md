---
title: "Разработка и развертывание служб WCF Data Services"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87a074b96583f44e8655c9efde145e28b490f6e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
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
  
 В этом разделе описывается в первую очередь разработка и развертывание служб данных с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Сведения о гибких возможностях [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] по предоставлению данных в виде каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] см. в разделе [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
### <a name="choosing-a-development-web-server"></a>Выбор веб-сервера развертывания  
 При разработке службы данных WCF в качестве приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или веб-узла [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]имеется выбор из веб-серверов, на которых можно запускать службы данных во время разработки. Следующие веб-серверы интегрируются с [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] , что упрощает тестирование и отладку служб данных на локальном компьютере.  
  
1.  **Локальный сервер служб IIS**  
  
     При создании службы данных, которая является приложением [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или веб-узлом [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , работающим на базе служб IIS, рекомендуется разрабатывать и тестировать службу данных с помощью IIS на локальном компьютере. Запуск службы данных в IIS упрощает трассировку HTTP-запросов во время отладки. Это также позволяет заранее определить необходимые права, которые требуются службам IIS для доступа к файлам, базам данных и другим ресурсам для службы данных. Для запуска службы данных в IIS необходимо проверить наличие и правильную настройку служб IIS и [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] , а также предоставить доступ учетным записям IIS к файловой системе и базам данных. Для получения дополнительной информации см. [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
    > [!NOTE]
    >  Необходимо запустить [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] с правами администратора, чтобы позволить среде разработки настроить локальный сервер IIS.  
  
2.  **Сервер разработки Visual Studio**  
  
     В состав[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] входит встроенный веб-сервер, сервер разработки [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] , который является веб-сервером по умолчанию для проектов [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . Этот веб-сервер предназначен для запуска проектов [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] на локальном компьютере во время разработки. В разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) показано создание службы данных, работающей на сервере разработки [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] .  
  
     При разработке службы данных с помощью сервера разработки [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] следует знать о следующих ограничениях.  
  
    -   Доступ к этому серверу возможен только с локального компьютера.  
  
    -   Этот сервер прослушивает `localhost` и указанный порт, отличный от порта 80, который по умолчанию настроен для HTTP-сообщений. Дополнительные сведения см. в разделе [Веб-серверы в Visual Studio для веб-проектов ASP.NET](http://msdn.microsoft.com/en-us/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
    -   На этом сервере служба данных работает в контексте текущей учетной записи пользователя. Например, при запуске пользователя уровня администратора служба данных, работающая на сервере разработки [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] , будет иметь права уровня администратора. Это может обеспечить службе данных доступ к ресурсам, для которых у нее не будет прав после развертывания на сервере служб IIS.  
  
    -   На этом сервере отсутствуют дополнительные возможности служб IIS, такие как проверка подлинности.  
  
    -   Этот сервер не может обрабатывать потоки HTTP частями, которые по умолчанию отправляются клиентом [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] при обращении к большим объемам двоичных данных из службы данных. Дополнительные сведения см. в разделе [потокового поставщика](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
    -   У этого сервера есть проблемы с обработкой символа точки (`.`) в URL-адресах, хотя этот символ и поддерживается [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в значениях ключа.  
  
    > [!TIP]
    >  Хотя можно использовать сервер разработки [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] для тестирования служб данных во время разработки, следует повторно их протестировать после развертывания на производственном веб-сервере, где запущены службы IIS.  
  
3.  **Среда разработки Microsoft Azure**  
  
     В состав средств Microsoft Azure для [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] входит интегрированный набор инструментов для развертывания служб Microsoft Azure в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. С помощью этих средств можно разрабатывать службы данных, которые могут развертываться на Microsoft Azure, а также тестировать службу данных на локальном компьютере перед развертыванием. Использование этих средств при развертывании службы данных, работающей на платформе Microsoft Azure, с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] . Загрузить средства Microsoft Azure для [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] можно из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=201848). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] разработке службы данных для запуска в Microsoft Azure см. в публикации блога [Deploying an OData Service in Microsoft Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="development-tips"></a>Советы по разработке  
 При разработке службы данных необходимо учитывать следующее:  
  
-   Определите требования по безопасности к службе данных, если планируется проверять подлинность пользователей или ограничивать доступ определенным пользователям. Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
-   Программа проверки HTTP может быть очень полезной при развертывании службы данных, позволяя проверять содержимое сообщений запросов и ответов. Любой планировщик сетевых пакетов, способный отображать необработанные пакеты, можно использовать для проверки HTTP-запросов к службе данных и ответов от нее.  
  
-   При отладке службы данных, возможно, потребуется получать от службы данных больше сведений об ошибках, чем при нормальной работе. Дополнительные сведения об ошибках можно получить из службы данных, установив свойство <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> в <xref:System.Data.Services.DataServiceConfiguration> значение `true` , а свойство <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> атрибута <xref:System.ServiceModel.Description.ServiceDebugBehavior> класса службы данных — в значение `true`. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] публикацию [Debugging WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=201868). Кроме того, можно включить трассировку в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для просмотра исключений, вызываемых уровнем сообщений HTTP. Для получения дополнительной информации см. [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   Служба данных обычно разрабатывается как проект приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , однако можно также создать службу данных как проект веб-узла [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Сведения о различиях между этими двумя типами проектов см. в статье [NIB.Сравнение проектов веб-приложений с проектами веб-сайтов в Visual Studio](http://msdn.microsoft.com/en-us/2861815e-f5a2-4378-a2f8-b8a86dc012f5).  
  
-   При создании службы данных с помощью диалогового окна **Добавление нового элемента** в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]служба данных будет размещаться [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] в IIS. Несмотря на то что [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и IIS используются для размещения службы данных по умолчанию, поддерживаются и другие варианты размещения. Дополнительные сведения см. в разделе [размещение служб данных](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).  
  
## <a name="deploying-wcf-data-services"></a>Развертывание служб данных WCF  
 Службы данных WCF обеспечивают гибкость в выборе процесса, в котором будет размещаться служба данных. Можно развертывать службу данных с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] на следующих платформах:  
  
-   **Веб-сервер, размещенный в службах IIS**  
  
     Если служба данных разрабатывается как проект [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , то его можно развернуть на веб-сервере IIS с помощью стандартной процедуры развертывания [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] обеспечивает следующие технологии развертывания для [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в зависимости от вида проекта [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , на котором размещена развертываемая служба данных.  
  
    -   **Технологии развертывания для веб-приложений ASP.NET**  
  
        -   [Пакет веб-развертывания](http://msdn.microsoft.com/en-us/1f9713c8-9540-494c-b80d-9893b970ad6f)  
  
        -   [Публикация одним щелчком](http://msdn.microsoft.com/en-us/59226246-99ad-4aec-975d-7c61e8a8911c)  
  
    -   **Технологии развертывания для веб-узлов ASP.NET**  
  
        -   [Средство копирования веб-узлов](http://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)  
  
        -   [Средство публикации веб-узлов](http://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)  
  
        -   [XCopy](http://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] вариантах развертывания для приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] см. в статье [Общие сведения о развертывании проектов веб-приложений для Visual Studio и ASP.NET](http://msdn.microsoft.com/en-us/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).  
  
    > [!TIP]
    >  Прежде чем пытаться выполнить развертывание службы данных в IIS, обязательно протестируйте развертывание на веб-сервере, где работают службы IIS. Для получения дополнительной информации см. [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
-   **Microsoft Azure**  
  
     Службу данных можно развертывать на Microsoft Azure с помощью средств Microsoft Azure для [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Загрузить средства Microsoft Azure для [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] можно из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=201848). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] развертывании службы данных в Microsoft Azure см. в публикации [Deploying an OData Service in Microsoft Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="deployment-considerations"></a>Требования к развертыванию  
 При разработке службы данных необходимо учитывать следующее:  
  
-   При развертывании службы данных, использующей поставщика [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] для доступа к базе данных SQL Server, можно также распространить структуры данных, данные или и то и другое. Для этого[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] может автоматически создать в целевой базе данных скрипты (SQL-файлы), которые можно включить в пакет веб-развертывания приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . Дополнительные сведения см. в статье [NIB. Практическое руководство. Развертывание базы данных с проектом веб-приложения](http://msdn.microsoft.com/en-us/683b33f1-8a3d-45cf-af6e-61ab50fc518b). Для веб-узла [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] это можно сделать с помощью **мастера публикации баз данных** в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Для получения дополнительной информации см. [Deploying a Database by Using the Database Publishing Wizard](http://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).  
  
-   Поскольку [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включает в себя базовую реализацию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , Windows Server AppFabric можно использовать для мониторинга службы данных, развернутой на IIS, работающем на Windows Server. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] использовании Windows Server AppFabric для наблюдения за службами данных см. в публикации [Tracking WCF Data Services with Windows Server AppFabri](http://go.microsoft.com/fwlink/?LinkID=202005).  
  
## <a name="see-also"></a>См. также  
 [Размещение служб данных](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 [Защита служб данных WCF](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
