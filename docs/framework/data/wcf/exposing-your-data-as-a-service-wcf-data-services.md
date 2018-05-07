---
title: Предоставление данных как службы (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 1ab349125419a0589d68ccb821009f8227c942e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a>Предоставление данных как службы (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируется с Visual Studio, чтобы можно было упрощает определение служб для предоставления данных в качестве [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-каналов. Создание службы данных, который предоставляет [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала состоит из следующих основных этапов:  
  
1.  **Определение** **модели данных**. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживаемые модели данных, которые основаны на [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Дополнительные сведения см. в разделе [как: создание службы данных с помощью источника данных Entity Framework ADO.NET](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживают также модели данных на основе объектов CLR, возвращающих экземпляр интерфейса <xref:System.Linq.IQueryable%601>. Это позволяет развертывать службы данных на основе списков, массивов и коллекций .NET Framework. Для поддержки создания, обновления и удаления элементов этих структур данных необходимо также реализовать интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [как: создание службы данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Для более сложных сценариев [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включает в себя набор поставщиков, которые позволяют определить модель данных на основе типов данных с поздним связыванием. Дополнительные сведения см. в разделе [настраиваемых поставщиков данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Создание службы данных.** Самая базовая служба данных предоставляет класс, производный от класса <xref:System.Data.Services.DataService%601> , с типом `T` , представляющим имя контейнера сущностей, квалифицированное пространством имен. Дополнительные сведения см. в разделе [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Настройка службы данных.** По умолчанию службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] запрещают доступ к ресурсам, предоставляемым контейнером сущностей. Интерфейс <xref:System.Data.Services.DataServiceConfiguration> позволяет настроить доступ к ресурсам и операциям службы, задать поддерживаемую версию [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], а также определить другие особенности поведения службы, такие как использование пакетирования или максимальное количество сущностей, которые могут быть возвращены в одном ответе. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Пример создания простой службы данных, основанный на образце базы данных "Борей" см. в разделе [краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Обзор набора средств Visual Studio для Unity](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
