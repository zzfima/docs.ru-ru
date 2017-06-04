---
title: "Создание поставщика данных Entity Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Создание поставщика данных Entity Framework
В этом разделе описывается порядок написания поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] для поддержки источников данных, отличных от [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] располагает поставщиком, поддерживающим [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## Знакомство с моделью поставщика Entity Framework  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] не зависит от баз данных, написать поставщика для подключения к различным источникам данных можно при помощи модели поставщика ADO.NE.  
  
 Поставщик данных Entity Framework \(созданный при помощи модели поставщика ADO.NET\) выполняет следующие функции.  
  
-   Сопоставляет примитивные типы модели EDM с типами поставщика.  
  
-   Предоставляет функции данного поставщика.  
  
-   Создает команды определенного поставщика для поддержки запросов [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbQueryCommandTree.  
  
-   Формирует команды обновления для определенного поставщика для поддержки обновлений через [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbModificationCommandTree.  
  
-   Предоставляет файлы сопоставления для определения схемы хранения для поддержки создания основанной на базе данных модели.  
  
-   Предоставляет метаданные \(например, таблицы и представления\) посредством концептуальной модели.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c\-0ac0\-4911\-86be\-0460a78760ba")  
  
## Пример  
 Пример поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], поддерживающего источник данных, кроме [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], см. в разделе [Образец поставщика Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) .  
  
## Содержание  
 [Создание SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [Создание кода SQL для изменения данных](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [Спецификация манифеста поставщика](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## См. также  
 [Работа с поставщиками данных](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)