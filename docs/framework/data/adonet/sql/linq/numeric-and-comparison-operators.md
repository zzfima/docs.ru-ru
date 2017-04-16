---
title: "Числовые операторы и операторы сравнения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Числовые операторы и операторы сравнения
Арифметические операторы и операторы сравнения работают в среде \(CLR\) соответствующим образом, за исключением следующих моментов.  
  
-   SQL не поддерживает оператор modulus для чисел с плавающей запятой.  
  
-   SQL не поддерживает непроверяемые арифметические операции.  
  
-   Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.  
  
## Поддерживаемые операторы  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает следующие операторы.  
  
-   Основные арифметические операторы  
  
    -   `+`  
  
    -   `-` \(вычитание\)  
  
    -   `*`  
  
    -   `/`  
  
    -   Оператор целочисленного деления Visual Basic \(`\`\)  
  
    -   `%` \(Visual Basic `Mod`\)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` \(унарное отрицание\)  
  
-   Основные операторы сравнения  
  
    -   Visual Basic `=` и C\# `==`  
  
    -   Visual Basic `<>` и C\# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## См. также  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)   
 [Операторы C\#](../Topic/C%23%20Operators.md)   
 [Операторы](../Topic/Operators%20\(Visual%20Basic\).md)