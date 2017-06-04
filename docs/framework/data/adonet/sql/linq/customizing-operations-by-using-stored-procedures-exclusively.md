---
title: "Настройка операций с использованием только хранимых процедур | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Настройка операций с использованием только хранимых процедур
Распространенным сценарием является доступ к данным с использованием только хранимых процедур.  
  
## Пример  
  
### Описание  
 Можно изменить пример, приведенный в разделе [Настройка операций с помощью хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md), заменив первый запрос \(который вызывает динамическое выполнение SQL\) на вызов метода, который служит оболочкой для хранимой процедуры.  
  
 Предположим, что `CustomersByCity` является методом, как в следующем примере.  
  
### Код  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Следующий код выполняется без динамического SQL.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## См. также  
 [Обязанности разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)