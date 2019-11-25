---
title: Предоставление данных как службы (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 71f26d7d41d112e13e6a77f0927c61d51b176b27
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975306"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Предоставление данных в качестве службы (WCF Data Services)

WCF Data Services интегрируется с Visual Studio, чтобы упростить определение служб для предоставления данных в виде веб-каналов Open Data Protocol (OData). Создание службы данных, предоставляющей канал OData, включает следующие основные шаги.

1. **Определите модель данных.** WCF Data Services изначально поддерживает модели данных, основанные на [Entity Frameworkе ADO.NET](../adonet/ef/index.md). Дополнительные сведения см. [в разделе инструкции. Создание службы данных с помощью источника данных ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md).

     WCF Data Services также поддерживает модели данных, основанные на объектах среды CLR, которые возвращают экземпляр интерфейса <xref:System.Linq.IQueryable%601>. Это позволяет развертывать службы данных на основе списков, массивов и коллекций .NET Framework. Для поддержки создания, обновления и удаления элементов этих структур данных необходимо также реализовать интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [инструкции. Создание службы данных с помощью поставщика отражения](create-a-data-service-using-rp-wcf-data-services.md).

     В более сложных сценариях WCF Data Services включает набор поставщиков, позволяющих определить модель данных на основе типов данных с поздним связыванием. Дополнительные сведения см. в разделе [пользовательские поставщики служб данных](custom-data-service-providers-wcf-data-services.md).

2. **Создайте службу данных.** Самая базовая служба данных предоставляет класс, производный от класса <xref:System.Data.Services.DataService%601> , с типом `T` , представляющим имя контейнера сущностей, квалифицированное пространством имен. Дополнительные сведения см. в разделе [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Настройте службу данных.** По умолчанию WCF Data Services отключает доступ к ресурсам, предоставляемым контейнером сущностей. Интерфейс <xref:System.Data.Services.DataServiceConfiguration> позволяет настроить доступ к ресурсам и операциям службы, указать поддерживаемую версию OData и определить другие поведения на уровне службы, например поведение пакетной обработки или максимальное число сущностей, которые могут быть возвращены в одном ответе. Дополнительные сведения см. [в разделе Настройка службы данных](configuring-the-data-service-wcf-data-services.md).

Пример создания простой службы данных, основанной на образце базы данных Northwind, см. в разделе [Краткое руководство](quickstart-wcf-data-services.md).

## <a name="see-also"></a>См. также

- [Начало работы](getting-started-with-wcf-data-services.md)
- [Обзор](wcf-data-services-overview.md)
