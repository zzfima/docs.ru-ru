---
title: Поставщик Entity Framework (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: a09c81b2d0f052884e8e54c899653a6f0e038aff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086251"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Поставщик Entity Framework (службы данных WCF)
Как и [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], платформа ADO.NET Entity Framework основана на модели EDM, которая представляет собой разновидность модели связей сущностей. Платформа Entity Framework преобразует операции собственной реализации модели EDM, который называется *концептуальной модели*, в эквивалентные операции в источнике данных. Это превращает Entity Framework в идеальный поставщик для служб данных на основе реляционных данных. Любая база данных, на которой имеется поставщик данных, поддерживающий Entity Framework, может использоваться совместно со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Список источников данных, которые поддерживают платформы Entity Framework, см. в разделе [сторонние поставщики для Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 В концептуальной модели контейнер сущностей является корнем службы. Прежде чем данные могут быть предоставлены службой данных, необходимо определить концептуальную модель Entity Framework. Дополнительные сведения см. в разделе [Как Создание службы данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживает модель оптимистичного параллелизма, позволяя определять маркер параллелизма для сущности. Этот маркер параллелизма, включающий одно или несколько свойств сущности, используется службой данных для определения, произошло ли изменение в запрашиваемых, обновляемых или удаляемых данных. Когда значения маркера, полученные из eTag в запросе, отличаются от текущих значений сущности, служба данных вызывает исключение. Чтобы указать, что свойство является частью маркера параллелизма, требуется применить атрибут `ConcurrencyMode="Fixed"` в модели данных, определенной поставщиком [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. Маркер параллелизма не может содержать ключевое свойство или свойство навигации. Дополнительные сведения см. в разделе [обновление службы данных](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Дополнительные сведения о платформе Entity Framework, см. в разделе [Обзор Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
## <a name="see-also"></a>См. также

- [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
- [EDM (модель данных с использованием сущностей)](../../../../docs/framework/data/adonet/entity-data-model.md)
