---
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 49d11556d3703331b4cdf5bf83a69f6b15bca8ed
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881995"
---
# <a name="quickstart-wcf-data-services"></a>Краткое руководство (службы данных WCF)

Это краткое руководство позволяет ознакомиться со службами данных WCF и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] через ряд задач, дополняющих содержимое разделов в [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Вы узнаете, как

Первая задача в этом кратком руководстве показано, как создать службу данных для предоставления каналов OData из образца базы данных "Борей". В последующих разделах вы будете обращаться к OData веб-канала с помощью веб-браузер, а также создавать Windows Presentation Foundation (WPF) клиентское приложение, использующее OData веб-канала с помощью клиентских библиотек.

## <a name="prerequisites"></a>Предварительные требования

Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:

- Visual Studio

- Экземпляр SQL Server. Это включает SQL Server Express, который включен по умолчанию при установке Visual Studio 2015, или как часть **хранение и обработка данных** рабочей нагрузки в Visual Studio 2017.

- Наличие учебной базы данных Northwind. Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).

## <a name="wcf-data-services-quickstart-tasks"></a>Задачи краткого руководства по служб данных WCF

 [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 Определите приложение ASP.NET, определите модель данных, создайте службу данных и включите доступ к ресурсам.

 [Доступ к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.

 [Создание клиентского приложения .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Создание приложения WPF для использования канала OData, привязка данных к элементам управления Windows, изменения данных в привязанных элементах управления и отправьте изменения обратно службе данных.

> [!NOTE]
> Файлы проекта, создаваемого при изучении краткого руководства, можно скачать на странице [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) (Образцы из документации по службам данных WCF).

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Начало выполнения краткого руководства](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)
