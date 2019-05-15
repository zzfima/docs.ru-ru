---
title: Размещение служб данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 4886103f7f0246eaacd12c3f12d50a055e650959
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582674"
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Размещение служб данных (службы данных WCF)
С помощью служб данных WCF, можно создать службу, предоставляющую данные в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала. Эта служба данных определена в качестве класса, наследуемого от <xref:System.Data.Services.DataService%601>. Этот класс предоставляет функциональность, необходимую для обработки сообщения запроса, выполнения обновлений в источнике данных и создания ответных сообщений, требует OData. Тем не менее службы данных невозможно привязать к и прослушивать входящие запросы HTTP к сетевому сокету. Реализацию этой обязательной функциональности служба данных возлагает на размещающий компонент.

 Узел службы данных выполняет следующие задачи от имени источника данных:

- Прослушивает запросы и перенаправляет их службе данных.

- Создает экземпляр службы данных для каждого запроса.

- Запрашивает обработку входящего запроса службой данных.

- Отправляет ответ от имени службы данных.

 Чтобы упростить размещение службы данных, службы данных WCF предназначен для интеграции с Windows Communication Foundation (WCF). Эта служба данных предоставляет реализацию по умолчанию WCF, который служит в качестве узла службы данных в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложения. Следовательно, службу данных можно разместить одним из следующих способов:

- В приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].

- В управляемом приложении, которое поддерживает резидентные службы WCF.

- В других специализированных узлах службы данных.

## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Размещение службы данных в приложении ASP.NET

При использовании **Добавление нового элемента** диалоговое окно в Visual Studio 2015 для определения службы данных в приложении ASP.NET, средство создает два новых файла в проекте. Первый файл имеет расширение `.svc` и определяет для среды выполнения WCF способ создания экземпляра службы данных. Ниже приведен пример этого файла для образца службы данных Northwind создана при выполнении [быстрого запуска](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):

```
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 Эта директива используется для инструкции приложения для создания узла службы для именованного класса службы данных путем использования класса <xref:System.Data.Services.DataServiceHostFactory>.

 Страница с выделенным кодом для файла `.svc` содержит класс, являющийся реализацией самой службы данных, определенной следующим образом для образца службы данных Northwind:

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 Поскольку служба данных работает аналогично службе WCF, она интегрируется с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и соответствует модели веб-программирования WCF. Дополнительные сведения см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) и [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).

## <a name="self-hosted-wcf-services"></a>Резидентные службы WCF
 Так как он включает в себя реализацию WCF, WCF Data Services поддерживают размещения службы данных в качестве службы WCF на собственном сервере. Службы могут быть размещены в любом приложении .NET Framework, например в консольном приложении. Класс <xref:System.Data.Services.DataServiceHost>, наследуемый от <xref:System.ServiceModel.Web.WebServiceHost>, используется для создания экземпляров службы данных по определенному адресу.

 Резидентное размещение можно использовать для разработки и тестирования, поскольку оно упрощает развертывание и диагностику службы. Однако этот тип размещения не обеспечивает дополнительные функции размещения и управления, обеспечиваемые [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или службами IIS. Дополнительные сведения см. в разделе [размещение в приложении управляемых](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).

## <a name="defining-a-custom-data-service-host"></a>Определение специализированных узлов служб данных
 В случае если ограничения, связанные с реализацией узла WCF, неприемлемы, для службы данных можно также определить настраиваемый узел. Любой класс, реализующий интерфейс <xref:System.Data.Services.IDataServiceHost>, можно использовать в качестве сетевого узла для службы данных. Настраиваемый узел должен реализовать интерфейс <xref:System.Data.Services.IDataServiceHost> и поддерживать следующие основные функции узла службы данных:

- Обеспечивать службу данных корневым путем службы.

- Обрабатывать данные заголовков запроса и ответа в соответствующей реализации элемента <xref:System.Data.Services.IDataServiceHost>.

- Обрабатывать исключения, сформированные службой данных.

- Проверять параметры в строке запроса.

## <a name="see-also"></a>См. также

- [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Предоставление данных как службы](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
- [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
