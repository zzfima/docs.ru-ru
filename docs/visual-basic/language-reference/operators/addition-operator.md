---
title: "Оператор + (Visual Basic) | Microsoft Docs"
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
  - "vb.+"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "+ - оператор"
  - "арифметические операторы, сложение"
  - "операторы объединения, синтаксис"
  - "строки [Visual Basic], сцепление"
  - "оператор суммирования"
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор + (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Складывает два числа или возвращает точное значение числового выражения.  Может также использоваться для сцепления двух строковых выражений.  
  
## Синтаксис  
  
```  
  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`expression1`|Обязательный.  Любое числовое или строковое выражение.|  
|`expression2`|Требуется, если оператор `+` не используется для вычисления отрицательного значения.  Любое числовое или строковое выражение.|  
  
## Результат  
 Если `expression1` и `expression2` оба являются о числовыми, то результатом является их арифметическая сумма.  
  
 Если `expression2` отсутствует, то оператор `+` является *унарным* оператором идентификатора для неизменяемого значения выражения.  В этом случае операция представляет собой сохранение знака выражения `expression1` таким образом, чтобы результат был отрицательным, если `expression1` было отрицательным.  
  
 Если `expression1` и `expression2` оба являются строками, результатом является объединение их значений.  
  
 Если `expression1` и `expression2` разных типов, то действие зависит от их типов, их содержимого и значения параметра [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  Дополнительные сведения см. в таблицах в разделе "Примечания".  
  
## Поддерживаемые типы  
 Все числовые типы, в том числе беззнаковые, с плавающей запятой, `Decimal` и `String`.  
  
## Заметки  
 В общем случае `+` выполняет арифметическое сложение, когда это возможно, и объединяет, только если оба выражения являются строками.  
  
 Если ни одно из двух выражений не является `Object`, Visual Basic выполняет следующие действия.  
  
|||  
|-|-|  
|Типы данных выражений|Действие компилятора|  
|Оба выражения являются числовыми типами данных \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` или `Double`\)|Сложение.  Тип данных результата является числовым типом, соответствующим типам данных выражений `expression1` и `expression2`.  См. таблицы "Целочисленные арифметические операции" в разделе [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип `String`|Объединение.|  
|Одно выражение — числовой тип данных, а второе — строка.|Если `Option Strict` имеет значение `On`, то создается ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, то можно неявно преобразовать `String` в `Double` и сложить.<br /><br /> Если `String` не может быть преобразовано в `Double`, создается исключение <xref:System.InvalidCastException>.|  
|Одно выражение числового типа данных, а второе — [Nothing](../../../visual-basic/language-reference/nothing.md)|Сложение, `Nothing` принимается за ноль.|  
|Одно выражение — строка, а второе — `Nothing`|Объединение, `Nothing` возвращает "".|  
  
 Если одно из выражений является выражением `Object`, Visual Basic выполняет следующие действия.  
  
|||  
|-|-|  
|Типы данных выражений|Действие компилятора|  
|Выражение `Object` содержит числовое значение и другое — числового типа данных.|Если `Option Strict` имеет значение `On`, то создается ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, то можно использовать сложение.|  
|Выражение `Object` содержит числовое значение и другое `String`|Если `Option Strict` имеет значение `On`, то создается ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, то можно неявно преобразовать `String` в `Double` и сложить.<br /><br /> Если `String` не может быть преобразовано в `Double`, создается исключение <xref:System.InvalidCastException>.|  
|Выражение `Object` содержит строку и другое — числового типа данных|Если `Option Strict` имеет значение `On`, то создается ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, то можно неявно преобразовать `Object` в `Double` и сложить.<br /><br /> Если `Object` не может быть преобразовано в `Double`, создается исключение <xref:System.InvalidCastException>.|  
|Выражение `Object` содержит строку, а другое имеет тип `String`|Если `Option Strict` имеет значение `On`, то создается ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, то можно неявно преобразовать `Object` в `String` и объединить.|  
  
 Если оба выражения являются `Object` выражениями, Visual Basic выполняет следующие действия \(только `Option Strict Off`\).  
  
|||  
|-|-|  
|Типы данных выражений|Действие компилятора|  
|Оба выражения `Object` содержат числовые значения|Сложение.|  
|Оба выражения `Object` имеют тип `String`|Объединение.|  
|Одно выражение `Object` содержит числовое значение, а другое содержит строку|Можно неявно преобразовать строку `Object` в `Double` и сложить.<br /><br /> Если строка `Object` не может быть преобразована в числовое значение, то создается исключение <xref:System.InvalidCastException>.|  
  
 Если любое из двух выражений `Object` принимает значение [Nothing](../../../visual-basic/language-reference/nothing.md) или <xref:System.DBNull>, то оператор `+` рассматривает его как `String` со значением "".  
  
> [!NOTE]
>  При использовании оператора `+` не всегда удается определить, произойдет объединение строк или операция сложения.  Чтобы избежать неоднозначности и получить самодокументирующий код, используйте для объединения оператор `&`.  
  
## Перегрузка  
 Оператор `+` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `+` используется для сложения чисел.  Если оба операнда являются числовыми, Visual Basic вычисляет арифметический результат.  Арифметический результат возвращает сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 Кроме того, имеется возможность использовать оператор `+` для объединения строк.  Если оба операнда являются строками, Visual Basic объединяет их.  Результат объединения представляет одну строку, состоящую из содержимого двух операндов \(один за другим\).  
  
 Если используются операнды разных типов, результат зависит от значения [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  В следующем примере показан результат, когда для `Option Strict` задано `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 В следующем примере показан результат, когда для `Option Strict` задано `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Чтобы избежать неоднозначности, при объединении следует использовать оператор `&` вместо `+`.  
  
## См. также  
 [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)