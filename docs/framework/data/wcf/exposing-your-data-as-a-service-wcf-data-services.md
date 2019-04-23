---
title: Предоставление данных как службы (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 3c0763f21940831f401194356dc25b0d99c8d6f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308540"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Предоставления данных как услуга (службы данных WCF)

Службы WCF Data Services интегрируется с Visual Studio, чтобы можно было упрощая определение служб для предоставления данных как [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-каналов. Создание службы данных, предоставляющего канал OData включает в себя следующие основные шаги:

1. **Определение модели данных.** Службы WCF Data Services изначально поддерживают модели данных, которые основаны на [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Дополнительные сведения см. в разделе [Как Создание службы данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).

     Службы WCF Data Services поддерживают также модели данных, на основании объекта (CLR) среды CLR, возвращающих экземпляр <xref:System.Linq.IQueryable%601> интерфейс. Это позволяет развертывать службы данных на основе списков, массивов и коллекций .NET Framework. Для поддержки создания, обновления и удаления элементов этих структур данных необходимо также реализовать интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [Как Создание службы данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).

     Для более сложных сценариев службы данных WCF включает в себя набор поставщиков, которые позволяют определить модель данных на основе типов данных с поздним связыванием. Дополнительные сведения см. в разделе [специализированные поставщики служб данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).

2. **Создание службы данных.** Самая базовая служба данных предоставляет класс, производный от класса <xref:System.Data.Services.DataService%601> , с типом `T` , представляющим имя контейнера сущностей, квалифицированное пространством имен. Дополнительные сведения см. в разделе [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3. **Настройка службы данных.** По умолчанию службы данных WCF запрещает доступ к ресурсам, предоставляемым контейнером сущностей. <xref:System.Data.Services.DataServiceConfiguration> Интерфейс позволяет настроить доступ к ресурсам и операциям службы, задать поддерживаемую версию OData и определить другие особенности поведения службы, такие как использование пакетирования или максимальное количество сущностей, которые могут быть возвращены в одном ответе. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

Пример создания простой службы данных, основанный на образце базы данных Northwind, см. в разделе [быстрого запуска](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

## <a name="see-also"></a>См. также

- [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [Обзор](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)