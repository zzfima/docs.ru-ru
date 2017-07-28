---
title: "Создание SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Создание SQL
При написании поставщика для [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] необходимо перевести дерево команд [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] на язык SQL, понятный базе данных, например Transact\-SQL для SQL Server или PL\/SQL для Oracle.  В этом разделе описано, как разрабатывать компонент создания кода SQL \(для запросов SELECT\) для поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Дополнительные сведения о вставке, обновлении и удалении запросов см. в разделе [Создание кода SQL для изменения данных](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).  
  
 Для усвоения данного раздела требуется знание [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и модели поставщика ADO.NET.  Также требуется знание деревьев команд и <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## Роль модуля создания кода SQL  
 Модуль создания кода SQ поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] переводит данное дерево команд запроса в одну инструкцию SQL SELECT, предназначенную для базы данных, которая совместима с SQL:1999.  В созданном коде SQL должно как можно меньше вложенных запросов.  Упрощение дерева команд выходного запроса в модуле создания кода SQL не допускается.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] может с этой целью, например, удалить соединения и свернуть последовательные узлы фильтра.  
  
 Класс <xref:System.Data.Common.DBProviderServices> является начальной точкой для доступа к уровню создания кода SQL для преобразования деревьев команд в <xref:System.Data.Common.DbCommands>.  
  
## Содержание  
 [Форма деревьев команд](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [Создание кода SQL из деревьев команд. Рекомендации](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [Создание кода SQL в образце поставщика](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## См. также  
 [Создание поставщика данных Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)