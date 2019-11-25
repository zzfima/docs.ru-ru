---
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: d0002182c5ae519c36348acdd2587bca499fe72e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975138"
---
# <a name="quickstart-wcf-data-services"></a>Краткое руководство (службы данных WCF)

Это краткое руководство поможет вам ознакомиться с WCF Data Services и Open Data Protocol (OData) с помощью серии задач, которые поддерживают разделы в [Начало работы](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Что вы узнаете

В первой задаче этого краткого руководства показано, как создать службу данных для предоставления веб-канала OData из образца базы данных Northwind. В последующих разделах вы получите доступ к каналу OData с помощью веб-браузера, а также создаете клиентское приложение Windows Presentation Foundation (WPF), которое использует канал OData с помощью клиентских библиотек.

## <a name="prerequisites"></a>Необходимые компоненты

Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:

- Visual Studio

- Экземпляр SQL Server. К ним относятся SQL Server Express, которые включены в установку Visual Studio 2015 по умолчанию или как часть рабочей нагрузки **хранения и обработки данных** в visual Studio 2017.

- Наличие учебной базы данных Northwind. Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).

## <a name="wcf-data-services-quickstart-tasks"></a>Краткие задачи служб данных WCF

 [Создание службы данных](creating-the-data-service.md)

 Определите приложение ASP.NET, определите модель данных, создайте службу данных и включите доступ к ресурсам.

 [Доступ к службе из веб-браузера](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.

 [Создание клиентского приложения .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Создание приложения WPF для использования веб-канала OData, привязки данных к элементам управления Windows, изменения данных в связанных элементах управления и последующей отправки изменений обратно в службу данных.

> [!NOTE]
> Файлы проекта, создаваемого при изучении краткого руководства, можно скачать на странице [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) (Образцы из документации по службам данных WCF).

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Запуск краткого руководства](creating-the-data-service.md)

## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../adonet/ef/index.md)
