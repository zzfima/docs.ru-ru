---
title: "Поставщик Entity Framework (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, поставщики"
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Поставщик Entity Framework (службы WCF Data Services)
Как и [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], платформа ADO.NET Entity Framework основана на модели EDM, которая представляет собой разновидность модели связей сущностей.  Entity Framework преобразует операции собственной реализации модели EDM, которая называется *концептуальной моделью*, в эквивалентные операции над источником данных.  Это превращает Entity Framework в идеальный поставщик для служб данных на основе реляционных данных. Любая база данных, на которой имеется поставщик данных, поддерживающий Entity Framework, может использоваться совместно со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Список источников данных, поддерживающих в настоящее время Entity Framework, см. в разделе [Поставщики сторонних производителей для Entity Framework](http://go.microsoft.com/fwlink/?LinkId=143699).  
  
 В концептуальной модели контейнер сущностей является корнем службы.  Прежде чем данные могут быть предоставлены службой данных, необходимо определить концептуальную модель Entity Framework.  Для получения дополнительной информации см. [Как создать службу данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживают модель оптимистичного параллелизма, позволяя определять токен параллелизма для сущности.  Этот маркер параллелизма, включающий одно или несколько свойств сущности, используется службой данных для определения, произошло ли изменение в запрашиваемых, обновляемых или удаляемых данных.  Когда значения маркера, полученные из eTag в запросе, отличаются от текущих значений сущности, служба данных вызывает исключение.  Чтобы указать, что свойство является частью маркера параллелизма, требуется применить атрибут `ConcurrencyMode="Fixed"` в модели данных, определенной поставщиком [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)].  Токен параллелизма не может включать ключевое свойство или свойство навигации. Дополнительные сведения см. в разделе [Обновление службы данных](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Дополнительные сведения о платформе Entity Framework см. в разделе [Общие сведения о платформе Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
## См. также  
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)