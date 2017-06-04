---
title: "Создание кода SQL в образце поставщика | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Создание кода SQL в образце поставщика
На примере [образца поставщика Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) демонстрируются новые компоненты поставщиков данных ADO.NET, которые поддерживают платформу [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.  
  
 Модуль создания кода SQL в образце поставщика \(расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs\) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.  
  
## Содержание  
 Этот раздел содержит следующие подразделы:  
  
 [Архитектура и разработка](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [Пошаговое руководство. Создание кода SQL](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## См. также  
 [Создание SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)