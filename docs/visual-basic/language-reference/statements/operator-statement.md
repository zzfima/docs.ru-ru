---
title: Operator Statement (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 69dea99cf71bd1e091116e54e244abfca291ffdb
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481979"
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
 Необязательный. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Обязательно. Указывает, что эта процедура оператора [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа.  
  
 `Overloads`  
 Необязательный. См. в разделе [перегружает](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Обязательно. Указывает, что эта процедура оператора [Shared](../../../visual-basic/language-reference/modifiers/shared.md) процедуры.  
  
 `Shadows`  
 Необязательный. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Требуется для оператора преобразования, если не указать `Narrowing`. Указывает, что эта процедура оператора определяет [Widening](../../../visual-basic/language-reference/modifiers/widening.md) преобразования. См. в разделе «Расширяющие и сужающие преобразования» на этой странице справки.  
  
 `Narrowing`  
 Требуется для оператора преобразования, если не указать `Widening`. Указывает, что эта процедура оператора определяет [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) преобразования. См. в разделе «Расширяющие и сужающие преобразования» на этой странице справки.  
  
 `operatorsymbol`  
 Обязательно. Символ или идентификатор оператора, который определяет Эта процедура оператора.  
  
 `operand1`  
 Обязательно. Имя и тип один операнд унарного оператора (включая оператор преобразования) или левого операнда бинарного оператора.  
  
 `operand2`  
 Требуется для бинарных операторов. Имя и тип правого операнда бинарного оператора.  
  
 `operand1` и `operand2` имеет следующие синтаксис и составляющие:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Отделение|Описание|  
|----------|-----------------|  
|`ByVal`|Необязательно, но механизм передачи должен быть [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Обязательно. Имя переменной, представляющей этот операнд. См. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Необязательный Если `Option Strict` является `On`. Тип данных этого операнда.|  
  
 `type`  
 Необязательный Если `Option Strict` является `On`. Возвращает тип данных значения, которое процедура оператора.  
  
 `statements`  
 Необязательный. Блок операторов, процедура оператора.  
  
 `returnvalue`  
 Обязательно. Значение, которое процедура оператора возвращает в вызывающий код.  
  
 `End` `Operator`  
 Обязательно. Завершает определение данной процедуры оператора.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Operator` только в классе или структуре. Это означает, что *контекст объявления* оператор не может быть исходный файл, пространство имен, модуля, интерфейса, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Все операторы должны быть `Public Shared`. Нельзя указать `ByRef`, `Optional`, или `ParamArray` для любой из операндов.  
  
 Нельзя использовать символ оператора или идентификатор для хранения возвращаемого значения. Необходимо использовать `Return` инструкции и его необходимо указать значение. Любое количество `Return` инструкций может находиться в любом в процедуре.  
  
 Определение оператора таким образом называется *перегрузка операторов*, независимо от того, имеется ли вы использовать `Overloads` ключевое слово. В приведенной ниже таблице перечислены операторы, которые можно определить.  
  
|Тип|Операторы|  
|----------|---------------|  
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Преобразование (унарный)|`CType`|  
  
 Обратите внимание, что `=` оператор в списке бинарных операторов является оператором сравнения, не оператором присваивания.  
  
 При определении `CType`, необходимо указать либо `Widening` или `Narrowing`.  
  
## <a name="matched-pairs"></a>Соответствующие пары  
 Некоторые операторы необходимо определить как пары. Если определен один оператор такой пары, необходимо определить другой. Ниже перечислены соответствующие пары.  
  
-   `=` и `<>`  
  
-   `>` и `<`  
  
-   `>=` и `<=`  
  
-   `IsTrue` и `IsFalse`  
  
## <a name="data-type-restrictions"></a>Ограничения типа данных  
 Каждый оператор должен включать класса или структуры, на котором его определить. Это означает, что класс или структура могут находиться только тип данных из следующих:  
  
-   Операнд унарного оператора.  
  
-   По крайней мере один из операндов бинарного оператора.  
  
-   Операнд или тип возвращаемого значения оператора преобразования.  
  
 Некоторые операторы имеют дополнительные ограничения типа данных, следующим образом:  
  
-   Если вы определяете `IsTrue` и `IsFalse` операторов, они должны возвращать `Boolean` типа.  
  
-   Если вы определяете `<<` и `>>` операторы, их необходимо указать `Integer` введите для `operandtype` из `operand2`.  
  
 В соответствии с типом один из операндов имеет тип возвращаемого значения. Например, оператор сравнения, такие как `=` или `<>` может возвращать `Boolean` даже если оба операнда являются `Boolean`.  
  
## <a name="logical-and-bitwise-operators"></a>Логические и побитовые операторы  
 `And`, `Or`, `Not`, И `Xor` операторы могут выполнять операции либо логическая или Битовая операция в Visual Basic. Тем не менее если один из этих операторов определяется для класса или структуры, можно определить только его побитовую операцию.  
  
 Не удается определить `AndAlso` оператор непосредственно с `Operator` инструкции. Тем не менее, можно использовать `AndAlso` Если выполнены следующие условия:  
  
-   Вы определили `And` с теми же типами операнд, который вы хотите использовать для `AndAlso`.  
  
-   Определение `And` возвращает совпадает с типом класса или структуры, на котором оно было настроено.  
  
-   Вы определили `IsFalse` оператора для класса или структуры, на котором вы определили `And`.  
  
 Аналогично, можно использовать `OrElse` Если вы определили `Or` на теми же операндами, определен с типом возвращаемого значения класса или структуры, и вы `IsTrue` для класса или структуры.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 Объект *расширяющее преобразование* всегда завершается успешно, во время выполнения, хотя *сужающее преобразование* может завершиться ошибкой во время выполнения. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 При объявлении процедуры преобразования `Widening`, ваш код процедуры не должны давать сбои. Это означает следующее.  
  
-   Оно должно всегда возвращать допустимое значение типа `type`.  
  
-   Он должен обрабатывать все возможные исключения и другие условия возникновения ошибок.  
  
-   Он должен обрабатывать любую ошибку, возвращаемую из любой процедуры, которые она вызывает.  
  
 Если есть вероятность того, что может произойти сбой процедуры преобразования, или что он может возникать необработанное исключение, необходимо объявить ее `Narrowing`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Operator` инструкции для определения контура структуры, которая включает в себя процедуры оператора `And`, `Or`, `IsFalse`, и `IsTrue` операторы. `And` и `Or` каждого используются два операнда типа `abc` и типом возвращаемого значения `abc`. `IsFalse` и `IsTrue` принимать одним операндом типа `abc` и возвращают `Boolean`. Эти определения позволяют вызывающий код для использования `And`, `AndAlso`, `Or`, и `OrElse` с операндами типа `abc`.  
  
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
