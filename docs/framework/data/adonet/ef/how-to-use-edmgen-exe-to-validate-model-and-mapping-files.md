---
title: "Как использовать EdmGen.exe для проверки модели и файлов сопоставления | Microsoft Docs"
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
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Как использовать EdmGen.exe для проверки модели и файлов сопоставления
В этом разделе описывается использование средства [Генератор EDM \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) для проверки файлов модели и сопоставления.  Для получения дополнительной информации см. [Модель EDM](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### Проверка модели School при помощи программы EdmGen.exe  
  
1.  Создайте базу данных School.  Для получения дополнительной информации см. [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Сформируйте модель School.  Для получения дополнительной информации см. [Как использовать средство EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```scr  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## См. также  
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ru-ru/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ru-ru/91076853-0881-421b-837a-f582f36be527)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/ru-ru/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [Как создать код уровня объектов с помощью программы EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)