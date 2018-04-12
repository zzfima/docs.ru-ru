---
title: Operator Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b6be45fd0a606f43c14d57f3f8ae0955f256ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="operator-statement"></a>Operator Statement
Объявляет символ оператора, операнды и код, которые определяют процедуру оператора для класса или структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a>Части  
 `attrlist`  
 Необязательно. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Обязательный. Указывает, что эта процедура оператора [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа.  
  
 `Overloads`  
 Необязательно. В разделе [перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Обязательный. Указывает, что эта процедура оператора [Shared](../../../visual-basic/language-reference/modifiers/shared.md) процедуры.  
  
 `Shadows`  
 Необязательно. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Требуется для оператора преобразования, если не указать `Narrowing`. Указывает, что эта процедура оператора определяет [Widening](../../../visual-basic/language-reference/modifiers/widening.md) преобразования. В разделе «Расширяющие и сужающие преобразования» на этой странице справки.  
  
 `Narrowing`  
 Требуется для оператора преобразования, если не указать `Widening`. Указывает, что эта процедура оператора определяет [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) преобразования. В разделе «Расширяющие и сужающие преобразования» на этой странице справки.  
  
 `operatorsymbol`  
 Обязательный. Символ или идентификатор оператора, который определяет Эта процедура оператора.  
  
 `operand1`  
 Обязательный. Имя и тип одного операнда унарного оператора (включая оператор преобразования) или левого операнда бинарного оператора.  
  
 `operand2`  
 Требуется для бинарных операторов. Имя и тип правого операнда бинарного оператора.  
  
 `operand1`и `operand2` имеет следующий синтаксис и компоненты:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Отделение|Описание|  
|----------|-----------------|  
|`ByVal`|Необязательно, но механизм передачи должен быть [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Обязательный. Имя переменной, представляющей этот операнд. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Необязательный Если `Option Strict` — `On`. Тип данных этого операнда.|  
  
 `type`  
 Необязательный Если `Option Strict` — `On`. Возвращает тип данных значения процедура оператора.  
  
 `statements`  
 Необязательно. Блок операторов, процедура оператора.  
  
 `returnvalue`  
 Обязательный. Значение, которое процедура оператора возвращает в вызывающий код.  
  
 `End` `Operator`  
 Обязательный. Завершает определение данной процедуры оператора.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Operator` только в классе или структуре. Это означает *контекст объявления* оператор не может быть исходный файл, пространство имен, модуля, интерфейса, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Все операторы должны быть `Public Shared`. Нельзя указать `ByRef`, `Optional`, или `ParamArray` для любой из операндов.  
  
 Нельзя использовать символ оператора или идентификатор для хранения возвращаемого значения. Необходимо использовать `Return` оператор, который необходимо указать значение. Любое количество `Return` операторы могут использоваться в любом месте в процедуре.  
  
 Определение оператора таким образом называется *перегрузка операторов*, независимо от того, имеется ли вы использовать `Overloads` ключевое слово. В приведенной ниже таблице перечислены операторы, которые можно определить.  
  
|Тип|Операторы|  
|----------|---------------|  
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Преобразование (унарный)|`CType`|  
  
 Обратите внимание, что `=` в списке бинарных является оператором сравнения, не оператором присваивания.  
  
 При определении `CType`, необходимо указать либо `Widening` или `Narrowing`.  
  
## <a name="matched-pairs"></a>Совпадающие пары  
 Необходимо определить определенные операторы как пары. Если определен один оператор такой пары, необходимо определить другой. Ниже перечислены соответствующие пары.  
  
-   `=` и `<>`.  
  
-   `>` и `<`  
  
-   `>=` и `<=`  
  
-   `IsTrue` и `IsFalse`.  
  
## <a name="data-type-restrictions"></a>Ограничения типа данных  
 Каждый оператор должен включать класса или структуры, в которой вы его определяете. Это означает, что класс или структура должно отображаться как тип данных из следующих:  
  
-   Операнд унарного оператора.  
  
-   По крайней мере один из операндов бинарного оператора.  
  
-   Операнд или тип возвращаемого значения оператора преобразования.  
  
 Некоторые операторы имеют дополнительные ограничения типа данных, как показано ниже:  
  
-   Если определить `IsTrue` и `IsFalse` операторов, они должны оба возвращать `Boolean` типа.  
  
-   Если определить `<<` и `>>` операторы, их необходимо указать `Integer` тип для `operandtype` из `operand2`.  
  
 Для соответствия типу одного из операндов имеет тип возвращаемого значения. Например, оператор сравнения, такие как `=` или `<>` может возвращать `Boolean` даже если оба операнда являются `Boolean`.  
  
## <a name="logical-and-bitwise-operators"></a>Логические и битовые операторы  
 `And`, `Or`, `Not`, И `Xor` операторы могут выполнять либо логические или битовые операции в Visual Basic. Тем не менее если определить один из этих операторов в классе или структуре, можно определить только его побитовую операцию.  
  
 Невозможно определить `AndAlso` оператор непосредственно с `Operator` инструкции. Тем не менее, можно использовать `AndAlso` Если выполнены следующие условия:  
  
-   Вы определили `And` с теми же типами операнд, который вы хотите использовать для `AndAlso`.  
  
-   Определение `And` возвращает совпадает с типом класса или структуры, на котором оно было настроено.  
  
-   Вы определили `IsFalse` оператор в классе или структуре, на котором вы определили `And`.  
  
 Аналогично, можно использовать `OrElse` Если вы определили `Or` на теми же операндами определили с возвращаемым типом класса или структуры, и `IsTrue` для класса или структуры.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 A *расширяющее преобразование* всегда успешно во время выполнения, хотя *сужающее преобразование* могут вызвать сбой во время выполнения. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 При объявлении процедуры преобразования быть `Widening`, ваш код процедуры не должен давать сбои. Это означает следующее.  
  
-   Оно должно всегда возвращать допустимое значение типа `type`.  
  
-   Он должен обрабатывать все возможные исключения и другие условия возникновения ошибок.  
  
-   Он должен обрабатывать любую ошибку, возвращаемую из любой процедуры, которые она вызывает.  
  
 Если есть вероятность того, что процедуры преобразования не может завершиться успешно, или что он может вызвать необработанное исключение, необходимо объявить ее `Narrowing`.  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Operator` инструкции для определения контура структуры, которая включает в себя процедуры оператора `And`, `Or`, `IsFalse`, и `IsTrue` операторы. `And`и `Or` каждый из которых принимает два операнда типа `abc` и тип возвращаемого значения `abc`. `IsFalse`и `IsTrue` каждый из которых принимает один операнд типа `abc` и возвращают `Boolean`. Эти определения позволяют вызывающий код, чтобы использовать `And`, `AndAlso`, `Or`, и `OrElse` с операндами типа `abc`.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Практическое руководство. Вызов процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [Практическое руководство. Использование класса, в котором определяются операторы](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
