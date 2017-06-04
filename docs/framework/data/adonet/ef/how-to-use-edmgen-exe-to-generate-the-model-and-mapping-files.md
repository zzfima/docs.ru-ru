---
title: "Как использовать средство EdmGen.exe для создания файлов модели и сопоставления | Microsoft Docs"
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
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Как использовать средство EdmGen.exe для создания файлов модели и сопоставления
В этом разделе показано, как с помощью средства «Генератор модели EDM» \(EdmGen.exe\) на основе базы данных School формируются следующие файлы:  
  
-   Концептуальная модель \(CSDL\-файл\).  
  
-   Модель хранения \(SSDL\-файл\).  
  
-   Сопоставление между концептуальной моделью и моделью хранения \(MSL\-файл\).  
  
-   Код уровня объекта в Visual Basic или C\#.  
  
-   Просмотр файлов.  
  
 Средство EdmGen.exe использует ключ \/mode:FullGeneration для создания перечисленных выше файлов.  Дополнительные сведения о командах средства EdmGen.exe см. в разделе [Генератор модели EDM \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 При использовании средства EdmGen.exe для формирования модели и файлов сопоставлений тем не менее необходимо настроить проект [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] на использование [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Для получения дополнительной информации см. [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ru-ru/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Концептуальная модель, созданная с помощью средства EdmGen.exe, включает все объекты базы данных.  При необходимости создания концептуальной модели, включающей только определенные объекты, следует использовать мастер моделей EDM.  Для получения дополнительной информации см. [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ru-ru/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### Создание модели School для проекта Visual Basic с помощью программы EdmGen.exe  
  
1.  Создайте базу данных School.  Для получения дополнительной информации см. [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
  
    ```  
  
### Создание модели School для проекта C\# с помощью программы EdmGen.exe  
  
1.  Создайте базу данных School.  Для получения дополнительной информации см. [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## См. также  
 [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ru-ru/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/ru-ru/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ru-ru/91076853-0881-421b-837a-f582f36be527)   
 [Как использовать EdmGen.exe для проверки модели и файлов сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)