---
title: Поставщик Entity Framework (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 612888aaa11c606112527f01864897560061845f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790846"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Поставщик Entity Framework (службы данных WCF)
Как и [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], платформа ADO.NET Entity Framework основана на модели EDM, которая представляет собой разновидность модели связей сущностей. Entity Framework преобразует операции в свою реализацию EDM, которая называется *концептуальной моделью*, в эквивалентные операции с источником данных. Это превращает Entity Framework в идеальный поставщик для служб данных на основе реляционных данных. Любая база данных, на которой имеется поставщик данных, поддерживающий Entity Framework, может использоваться совместно со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Список источников данных, которые в настоящее время поддерживают Entity Framework, см. [в разделе сторонние поставщики для Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 В концептуальной модели контейнер сущностей является корнем службы. Прежде чем данные могут быть предоставлены службой данных, необходимо определить концептуальную модель Entity Framework. Дополнительные сведения см. в разделе [Практическое руководство. Создайте службу данных с помощью источника](create-a-data-service-using-an-adonet-ef-data-wcf.md)данных ADO.NET Entity Framework.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]поддерживает модель оптимистичного параллелизма, позволяя определить маркер параллелизма для сущности. Этот маркер параллелизма, включающий одно или несколько свойств сущности, используется службой данных для определения, произошло ли изменение в запрашиваемых, обновляемых или удаляемых данных. Когда значения маркера, полученные из eTag в запросе, отличаются от текущих значений сущности, служба данных вызывает исключение. Чтобы указать, что свойство является частью маркера параллелизма, требуется применить атрибут `ConcurrencyMode="Fixed"` в модели данных, определенной поставщиком [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. Маркер параллелизма не может содержать ключевое свойство или свойство навигации. Дополнительные сведения см. [в разделе Обновление службы данных](updating-the-data-service-wcf-data-services.md).  
  
 Дополнительные сведения о Entity Framework см. в разделе [Общие сведения о Entity Framework](../adonet/ef/overview.md).  
  
## <a name="see-also"></a>См. также

- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
- [Поставщик отражений](reflection-provider-wcf-data-services.md)
- [Сущностная модель данных](../adonet/entity-data-model.md)
