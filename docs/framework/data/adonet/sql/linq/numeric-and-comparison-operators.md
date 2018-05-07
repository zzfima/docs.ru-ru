---
title: Числовые операторы и операторы сравнения
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a1ce13225d72b4286982434d52998a1913814abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
