---
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f20ffcf356aa0493b1e2356746d9ad7b27d9a1aa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504566"
---
# <a name="quickstart-wcf-data-services"></a>Краткое руководство (службы данных WCF)

Это краткое руководство позволяет ознакомиться со службами данных WCF и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] через ряд задач, дополняющих содержимое разделов в [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Вы узнаете, как

Первая задача в этом кратком руководстве показано, как создать службу данных для предоставления каналов OData из образца базы данных "Борей". В последующих разделах вы будете обращаться к OData веб-канала с помощью веб-браузер, а также создавать Windows Presentation Foundation (WPF) клиентское приложение, использующее OData веб-канала с помощью клиентских библиотек.

## <a name="prerequisites"></a>Предварительные требования

Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:

- Visual Studio

- Экземпляр SQL Server. Это включает SQL Server Express, который включен по умолчанию при установке Visual Studio 2015, или как часть **хранение и обработка данных** рабочей нагрузки в Visual Studio 2017.

- Наличие учебной базы данных Northwind. Чтобы скачать этот образец базы данных, см. на странице загрузки [образцы баз данных для SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).

## <a name="wcf-data-services-quickstart-tasks"></a>Задачи краткого руководства по служб данных WCF

 [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 Определите приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , определите модель данных, создайте службу данных и включите доступ к ресурсам.

 [Доступ к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.

 [Создание клиентского приложения .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Создание приложения WPF для использования канала OData, привязка данных к элементам управления Windows, изменения данных в привязанных элементах управления и отправьте изменения обратно службе данных.

> [!NOTE]
> Файлы проекта из полной версии краткого руководства можно загрузить из [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) страницы.

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Начало выполнения краткого руководства](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)
