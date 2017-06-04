---
title: "Как определить строки соединения. | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как определить строки соединения.
В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели.  Описание в этом разделе построено на основе концептуальной модели [AdventureWorks Sales](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  Модель AdventureWorks Sales используется во всех разделах документации платформы [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], связанных с выполнением задач.  Материал этого раздела подразумевает, что настроена платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и определена модель AdventureWorks Sales.  Для получения дополнительной информации см. [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/ru-ru/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  Процедуры этого раздела также включены в раздел [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ru-ru/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  При использовании мастера [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] в проекте [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] он автоматически сформирует EDMX\-файл и настроит проект для использования платформы [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Дополнительные сведения см. в разделе [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ru-ru/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### Определение строки соединения Entity Framework  
  
-   Откройте файл конфигурации приложения \(app.config\) и добавьте следующую строку соединения:  
  
  
  
     Если проект не содержит файла конфигурации приложения, его можно добавить, выбрав в меню **Проект** команду **Добавить новый элемент**, затем в категории **Общие** выбрать **Файл конфигурации приложения** и нажать кнопку **Добавить**.  
  
## См. также  
 [Quickstart](http://msdn.microsoft.com/ru-ru/0bc534be-789f-4819-b9f6-76e51d961675)   
 [How to: Create a New .edmx File](http://msdn.microsoft.com/ru-ru/beb8189e-e51c-4051-839c-9902c224abf2)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ru-ru/91076853-0881-421b-837a-f582f36be527)