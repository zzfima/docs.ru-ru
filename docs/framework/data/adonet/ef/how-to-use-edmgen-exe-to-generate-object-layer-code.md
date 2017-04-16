---
title: "Как создать код уровня объектов с помощью программы EdmGen.exe | Microsoft Docs"
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
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Как создать код уровня объектов с помощью программы EdmGen.exe
В этом разделе показано, как с помощью [генератора модели EDM \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) сформировать код уровня объектов на основе CSDL\-файла.  
  
### Создание кода уровня объекта для модели School в проекте Visual Basic с помощью EdmGen.exe  
  
1.  Создайте базу данных School.  Для получения дополнительной информации см. [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Создайте модель School или получите файл School.csdl.  Для получения дополнительной информации см. [Как использовать средство EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### Создание кода уровня объектов для модели School в проекте С\# с помощью программы EdmGen.exe  
  
1.  Создайте базу данных School.  Для получения дополнительной информации см. [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Создайте модель School или получите файл School.csdl.  Для получения дополнительной информации см. [Как использовать средство EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## См. также  
 [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ru-ru/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ru-ru/91076853-0881-421b-837a-f582f36be527)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/ru-ru/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [Как использовать средство EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)