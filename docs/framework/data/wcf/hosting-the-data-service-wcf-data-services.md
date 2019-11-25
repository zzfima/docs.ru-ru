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
ms.openlocfilehash: 3abcd901bcb8a175aa6f30e53b142cbbde56a579
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975246"
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Размещение служб данных (службы данных WCF)
С помощью WCF Data Services можно создать службу, которая предоставляет данные в виде веб-канала Open Data Protocol (OData). Эта служба данных определена в качестве класса, наследуемого от <xref:System.Data.Services.DataService%601>. Этот класс предоставляет функции, необходимые для обработки сообщений запросов, выполнения обновлений для источника данных и создания сообщений ответов в соответствии с требованиями OData. Однако службе данных не удается выполнить привязку и прослушивание сетевого сокета для входящих HTTP-запросов. Реализацию этой обязательной функциональности служба данных возлагает на размещающий компонент.

 Узел службы данных выполняет следующие задачи от имени источника данных:

- Прослушивает запросы и перенаправляет их службе данных.

- Создает экземпляр службы данных для каждого запроса.

- Запрашивает обработку входящего запроса службой данных.

- Отправляет ответ от имени службы данных.

 Для упрощения размещения службы данных WCF Data Services предназначен для интеграции с Windows Communication Foundation (WCF). Служба данных предоставляет реализацию WCF по умолчанию, которая служит узлом службы данных в приложении ASP.NET. Следовательно, службу данных можно разместить одним из следующих способов:

- В приложении ASP.NET.

- В управляемом приложении, которое поддерживает резидентные службы WCF.

- В других специализированных узлах службы данных.

## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Размещение службы данных в приложении ASP.NET

При использовании диалогового окна **Добавление нового элемента** в Visual Studio 2015 для определения службы данных в приложении ASP.NET это средство создает два новых файла в проекте. Первый файл имеет расширение `.svc` и определяет для среды выполнения WCF способ создания экземпляра службы данных. Ниже приведен пример этого файла для образца службы данных Northwind, созданного при выполнении [краткого руководства](quickstart-wcf-data-services.md).

```aspx-csharp
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

 Так как служба данных ведет себя как служба WCF, служба данных интегрируется с ASP.NET и соответствует модели веб-программирования WCF. Дополнительные сведения см. в статьях [службы WCF и ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) и [модель программирования веб-HTTP WCF](../../wcf/feature-details/wcf-web-http-programming-model.md).

## <a name="self-hosted-wcf-services"></a>Резидентные службы WCF
 Так как она включает реализацию WCF, WCF Data Services поддерживает самостоятельное размещение службы данных в качестве службы WCF. Служба может быть размещена самостоятельно в любом приложении .NET Framework, например в консольном приложении. Класс <xref:System.Data.Services.DataServiceHost>, наследуемый от <xref:System.ServiceModel.Web.WebServiceHost>, используется для создания экземпляров службы данных по определенному адресу.

 Резидентное размещение можно использовать для разработки и тестирования, поскольку оно упрощает развертывание и диагностику службы. Однако этот тип размещения не предоставляет расширенные функции размещения и управления, предоставляемые ASP.NET или службы IIS (IIS). Дополнительные сведения см. [в разделе Размещение в управляемом приложении](../../wcf/feature-details/hosting-in-a-managed-application.md).

## <a name="defining-a-custom-data-service-host"></a>Определение специализированных узлов служб данных
 В случае если ограничения, связанные с реализацией узла WCF, неприемлемы, для службы данных можно также определить настраиваемый узел. Любой класс, реализующий интерфейс <xref:System.Data.Services.IDataServiceHost>, можно использовать в качестве сетевого узла для службы данных. Настраиваемый узел должен реализовать интерфейс <xref:System.Data.Services.IDataServiceHost> и поддерживать следующие основные функции узла службы данных:

- Обеспечивать службу данных корневым путем службы.

- Обрабатывать данные заголовков запроса и ответа в соответствующей реализации элемента <xref:System.Data.Services.IDataServiceHost>.

- Обрабатывать исключения, сформированные службой данных.

- Проверять параметры в строке запроса.

## <a name="see-also"></a>См. также

- [Определение служб данных WCF](defining-wcf-data-services.md)
- [Предоставление данных как службы](exposing-your-data-as-a-service-wcf-data-services.md)
- [Настройка службы данных](configuring-the-data-service-wcf-data-services.md)
