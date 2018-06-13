---
title: Функция CType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 7b1c7ae2a0126bf7cd487df4e9a7364c98e1c695
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603023"
---
# <a name="ctype-function-visual-basic"></a>Функция CType (Visual Basic)
Возвращает результат явного преобразования выражения для указанного типа данных, объекта, структуры, класса или интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a>Части  
 `expression`  
 Любое допустимое выражение. Если значение `expression` находится за пределами диапазона, разрешенного `typename`, Visual Basic создает исключение.  
  
 `typename`  
 Любое выражение, которое является допустимым в `As` предложения в `Dim` инструкции, то есть имя типа данных, объекта, структуры, класса или интерфейса.  
  
## <a name="remarks"></a>Примечания  
  
> [!TIP]
>  Для выполнения преобразования типов также можно использовать следующие функции:  
>   
>  -   Функции преобразования типов, такие как `CByte`, `CDbl`, и `CInt` , выполнить преобразование в определенный тип данных. Дополнительные сведения см. в разделе [функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
> -   [Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Эти операторы требуют наследовать от одного типа или реализовывал другой тип. Они могут предоставить немного лучшую производительность, чем `CType` при преобразовании к и из `Object` тип данных.  
  
 `CType` — скомпилированные встроенный, это означает, что код преобразования является частью кода, вычисляет выражение. В некоторых случаях код выполняется быстрее, так как процедуры не вызываются для выполнения преобразования.  
  
 Если не определено преобразование из `expression` для `typename` (например, из `Integer` для `Date`), Visual Basic выводит сообщение об ошибке времени компиляции.  
  
 Если преобразование завершается ошибкой во время выполнения, соответствующее исключение. При сбое преобразования с сужением <xref:System.OverflowException> наиболее распространенные результат. Если преобразование не определен, <xref:System.InvalidCastException> в исключение. Например, это может произойти, если `expression` относится к типу `Object` и его тип времени выполнения не имеет преобразования в `typename`.  
  
 Если тип данных `expression` или `typename` — это класс или структуру, вы определили, можно определить `CType` в этом классе или структуре, что оператор преобразования. Это делает `CType` выступать в качестве *перегруженный оператор*. После этого можно управлять поведением преобразования в и из класса или структуры, включая исключения, которые могут быть созданы.  
  
## <a name="overloading"></a>Перегрузка  
 `CType` Оператора для класса или структуры, определяемая вне кода также может быть перегружен. Если код осуществляет преобразование в или из класса или структуры, убедитесь, что вы понимаете поведение его `CType` оператор. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="converting-dynamic-objects"></a>Преобразование динамических объектов  
 Тип преобразования динамических объектов выполняются через заданные пользователем преобразования динамических, использующих <xref:System.Dynamic.DynamicObject.TryConvert%2A> или <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> методы. Если вы работаете с динамическими объектами, используйте <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> метод для преобразования динамического объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `CType` функцию для преобразования выражения `Single` тип данных.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 Дополнительные примеры см. в разделе [неявные и явные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Функции преобразования](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Преобразование типов в .NET Framework](../../../standard/base-types/type-conversion.md)
