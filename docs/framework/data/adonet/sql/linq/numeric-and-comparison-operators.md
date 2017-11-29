---
title: "Числовые операторы и операторы сравнения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f77cb612468b401f6aa526e46cc7481d0b47d385
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-and-comparison-operators"></a>Числовые операторы и операторы сравнения
Арифметические операторы и операторы сравнения работают в среде (CLR) соответствующим образом, за исключением следующих моментов.  
  
-   SQL не поддерживает оператор modulus для чисел с плавающей запятой.  
  
-   SQL не поддерживает непроверяемые арифметические операции.  
  
-   Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.  
  
## <a name="supported-operators"></a>Поддерживаемые операторы  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает следующие операторы.  
  
-   Основные арифметические операторы  
  
    -   `+`  
  
    -   `-` (вычитание)  
  
    -   `*`  
  
    -   `/`  
  
    -   Оператор целочисленного деления Visual Basic (`\`)  
  
    -   `%` (Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` (унарное отрицание)  
  
-   Основные операторы сравнения  
  
    -   Visual Basic `=` и C# `==`  
  
    -   Visual Basic `<>` и C# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>См. также  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [Операторы в C#](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [Операторы](../../../../../visual-basic/language-reference/operators/index.md)
