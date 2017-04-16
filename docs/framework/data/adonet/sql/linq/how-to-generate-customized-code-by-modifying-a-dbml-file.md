---
title: "Как создать настраиваемый код путем изменения DBML-файла | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как создать настраиваемый код путем изменения DBML-файла
Исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C\# можно создать из DBML\-файла метаданных.  Этот способ предоставляет возможность настройки заданного по умолчанию DBML\-файла до создания кода сопоставления приложений.  Данная возможность является дополнительной.  
  
 Ниже указаны действия, необходимые для выполнения данного процесса.  
  
1.  Создайте DBML\-файл.  
  
2.  Для изменения DBML\-файла используйте редактор.  Обратите внимание, что DBML\-файл должен быть проверен на соответствие файлу определения схемы \(XSD\) для DBML\-файлов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Для получения дополнительной информации см. [Создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Создайте исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C\#.  
  
 В следующих примерах используется средства командной строки SQLMetal.  Для получения дополнительной информации см. [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Пример  
 В следующем коде DBML\-файл создается из учебной базы данных "Northwind".  В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF\-файла.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## Пример  
 В следующем коде исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C\# создается из DBML\-файла.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## См. также  
 [Создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)   
 [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)   
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)