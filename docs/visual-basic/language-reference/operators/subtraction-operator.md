---
title: "Оператор - (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Negate"
  - "vb.-"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "- - оператор [Visual Basic]"
  - "арифметические операторы, вычитание"
  - "оператор разности"
  - "математические операторы"
  - "minus - оператор [Visual Basic]"
  - "оператор отрицания"
  - "операторы [Visual Basic], арифметические"
  - "операторы [Visual Basic], различие"
  - "операторы [Visual Basic], отрицание"
  - "операторы [Visual Basic], вычитание"
  - "оператор вычитания, синтаксис"
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор - (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возвращает значение разности между двумя числовыми выражениями или отрицательное значение числового выражения.  
  
## Синтаксис  
  
```  
  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## Части  
 `expression1`  
 Обязательный.  Произвольное числовое выражение.  
  
 `expression2`  
 Требуется, если оператор `–` не используется для вычисления отрицательного значения.  Произвольное числовое выражение.  
  
## Результат  
 Результатом является разность между `expression1` и `expression2` или отрицательное значение выражения `expression1`.  
  
 Тип данных результата является числовым типом, соответствующим типам данных выражений `expression1` и `expression2`.  См. таблицы "Целочисленные арифметические операции" в разделе [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## Поддерживаемые типы  
 Все числовые типы.  К ним относятся типы чисел с плавающей запятой и без знака и тип `Decimal`.  
  
## Заметки  
 При первом использовании в приведенном примере оператор `–` является оператором *двоичного* арифметического вычитания для нахождения разности двух числовых выражений.  
  
 При втором использовании в предыдущем примере оператор `–` является *унарным* оператором отрицания для вычисления отрицательного значения выражения.  В этом случае отрицание представляет собой замену знака выражения `expression1` таким образом, чтобы результат был положительным, если `expression1` было отрицательным.  
  
 Если выражение примет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оператор `–` интерпретирует его как ноль.  
  
> [!NOTE]
>  Оператор `–` может быть *перегружен*. Это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `–` вычисляет и возвращает разность двух чисел, а затем меняет знак числа.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 После выполнения этих инструкций параметр `binaryResult` содержит значение 124,45, а параметр `unaryResult` содержит значение –334,90.  
  
## См. также  
 [Оператор \-\=](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)