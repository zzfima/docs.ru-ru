---
title: "Функция CType (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "результат преобразования выражения"
  - "явное преобразование типов данных"
  - "CType - функция"
  - "преобразования, выражение"
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Функция CType (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Возвращает результат явного преобразования выражения в заданный тип данных, объект, структуру, класс или интерфейс.  
  
## Синтаксис  
  
```  
CType(expression, typename)  
```  
  
## Части  
 `expression`  
 Любое допустимое выражение.  Если значение `expression` находится вне диапазона, разрешенного `typename`, то Visual Basic создает исключение.  
  
 `typename`  
 Любое корректное выражение, с оператором `As` в операторе `Dim`, т.е. имя любого типа данных, объекта, структуры, класса или интерфейса.  
  
## Заметки  
  
> [!TIP]
>  Следующие функции также можно использовать для выполнения преобразования типов:  
>   
>  -   Функции преобразования типа, например `CByte`, `CDbl` и `CInt`, которые выполняют преобразование к определенному типу данных.  Для получения дополнительной информации см. [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
> -   [Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  Эти операторы требуют наследования одного типа и реализации другого типа.  Они могут предоставлять несколько более высокую производительность, чем `CType` при преобразовании значений с типом данных `Object`.  
  
 Функция `CType` компилируется путем подстановки кода. Это означает, что код преобразования является частью кода, предназначенного для вычисления выражения.  В некоторых случаях код выполняется быстрее, потому что процедуры для выполнения преобразования не вызываются.  
  
 Если не определено преобразование из `expression` в `typename` \(например из `Integer` в `Date`\), то Visual Basic отображает сообщение об ошибке времени компиляции.  
  
 При сбое преобразования во время выполнения возникает соответствующее исключение.  При сбое сужающего преобразования наиболее частым результатом является <xref:System.OverflowException>.  Если преобразование не определено, возникает <xref:System.InvalidCastException>.  Например, это может произойти, если `expression` имеет тип `Object` и его тип времени выполнения не имеет преобразования в `typename`.  
  
 Если тип данных `expression` или `typename` — класс или структура, можно определить `CType` для этих класса или структуры в качестве оператора преобразования.  Это заставляет `CType` выполняться как *перегруженный оператор*.  В этом случае можно управлять поведением преобразования в класс или структуру и обратно, включая то, какие исключения могут создаваться.  
  
## Перегрузка  
 Оператор `CType` также может быть перегружен для класса или структуры, определяемой вне данного кода.  Если код осуществляет преобразование в или из такого класса или структуры, то необходимо понять поведение его оператора `CType`.  Для получения дополнительной информации см. [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Преобразование динамических объектов  
 Преобразования типов динамических объектов выполняются динамически определяемыми пользователем преобразованиями, использующего методы <xref:System.Dynamic.DynamicObject.TryConvert%2A> или <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>.  При работе с динамическими объектами, используйте метод <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> для преобразования динамический объект.  
  
## Пример  
 В этом примере функция `CType` используется для приведения выражения к типу данных `Single`.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 Дополнительные примеры см. в разделе [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## См. также  
 <xref:System.OverflowException>   
 <xref:System.InvalidCastException>   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Функции преобразования](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Преобразование типов в .NET Framework](../Topic/Type%20Conversion%20in%20the%20.NET%20Framework.md)