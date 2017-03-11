---
title: "Оператор &gt;&gt;= (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.>>="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - ">>= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - ">>= - оператор [Visual Basic]"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор &gt;&gt;= (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Производит арифметический сдвиг вправо значения переменной или свойства и присваивает результат этой переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty >>= amount  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Переменная или свойство целого типа \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` или `ULong`\).  
  
 `amount`  
 Обязательный.  Цифровое значение с типом данных, расширяемым до `Integer`.  
  
## Заметки  
 Элемент с левой стороны оператора `>>=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Сначала выполняет арифметический оператор `>>=` верный переход на значение переменной или свойства.  Оператор затем присвоить результат этой операции обратно в переменную или свойству.  
  
 Арифметические сдвиги не являются циклическими. Это означает, что биты, сдвинутые в один конец результата, не вводятся повторно в другой конец.  При арифметическом сдвиге вправо, биты, сдвигаемые дальше первой справа позиции, теряются, а место, освобождаемое слева, замещается значением первого бита слева.  Это значит, что если `variableorproperty` имеет отрицательное значение, освобождаемые позиции устанавливаются в единицу.  Если `variableorproperty` имеет положительное значение или беззнаковое, освобождаемые биты устанавливаются в ноль.  
  
## Перегрузка  
 [Оператор \>\>](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружен*. Это означает, что класс или структура может переопределить его действие, если операнд имеет такой же тип класса или структуры.  Перегрузка оператора `>>` влияет на тип выполнения оператора `>>=`.  Если в коде используется оператор `>>=` для класса или структуры, перегружающей `>>`, убедитесь, что его переопределенное выполнение понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 Следующий пример демонстрирует использование оператора `>>=` для сдвига битовой структуры переменной типа `Integer` вправо с присвоением результирующего значения переменной.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/right-shift-assignment-o_1_1.vb)]  
  
## См. также  
 [Оператор \>\>](../../../visual-basic/language-reference/operators/right-shift-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Операторы поразрядного сдвига](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)