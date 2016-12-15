---
title: "Оператор &lt;&lt;= (Visual Basic) | Microsoft Docs"
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
  - "vb.<<="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<<= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "<<= - оператор"
  - "<<= - оператор"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор &lt;&lt;= (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Производит арифметический сдвиг значения переменной или свойcтва влево и присваивает результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty <<= amount  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Переменная или свойство целого типа \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` или `ULong`\).  
  
 `amount`  
 Обязательный.  Цифровое значение с типом данных, расширяемым до `Integer`.  
  
## Заметки  
 Элемент с левой стороны оператора `<<=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `<<=` сначала выполняет арифметический оператор left миграция на значение переменной или свойства.  Оператор затем присвоить результат этой операции назад в разделах переменной или свойству.  
  
 Арифметические сдвиги не являются циклическими. Это означает, что биты, сдвинутые в один конец результата, не вводятся повторно в другой конец.  В арифметическом левом сдвиге биты, сдвинутые за пределы диапазона типа данных результата, отбрасываются, а освободившиеся справа позиции битов задаются как нули.  
  
## Перегрузка  
 [Оператор \<\<](../../../visual-basic/language-reference/operators/left-shift-operator.md) может быть *перегружен*. Это означает, что класс или структура может переопределить его действие, если операнд имеет такой же тип класса или структуры.  Перегрузка оператора `<<` влияет на тип выполнения оператора `<<=`.  Если в коде используется оператор `<<=` для класса или структуры, перегружающей `<<`, убедитесь, что его переопределенное выполнение понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 Следующий пример демонстрирует использование оператора `<<=` для сдвига битовой структуры переменной типа `Integer` влево с присвоением результирующего значения переменной.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор \<\<](../../../visual-basic/language-reference/operators/left-shift-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Операторы поразрядного сдвига](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)