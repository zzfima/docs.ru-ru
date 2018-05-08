---
title: Оператор DirectCast (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 534e94ecc0a394caa2865c2da754ad8f4dbc6f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="directcast-operator-visual-basic"></a>Оператор DirectCast (Visual Basic)
Вводит операцию преобразования типа на основе наследования или реализации.  
  
## <a name="remarks"></a>Примечания  
 `DirectCast` не используйте в Visual Basic подпрограммы поддержки времени выполнения для преобразования, поэтому она обеспечивает немного лучшую производительность, чем `CType` при преобразовании из типа данных и `Object`.  
  
 Вы используете `DirectCast` аналогично тому, как использовать ключевое слово [функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) ключевое слово. Можно указать выражение в качестве первого аргумента и тип для преобразования его в качестве второго аргумента. `DirectCast` требуется отношение наследования или реализации между типами данных обоих аргументов. Это означает, что один тип должен реализовывать или наследовать из другого.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `DirectCast` создает ошибку компилятора, если он обнаруживает, что существует отношение наследования или реализации. Однако отсутствие ошибки компилятора не гарантирует успешное преобразование. Если требуемое преобразование будет сужающим, то возможен сбой во время выполнения. В этом случае среда выполнения создает <xref:System.InvalidCastException> ошибки.  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Сравнение ключевых слов преобразования типов выглядит следующим образом.  
  
|Ключевое слово|Типы данных|Отношение аргументов|Ошибка времени выполнения|  
|---|---|---|---|  
|[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Типы данных|Должен быть определен расширяющее или сужающее преобразование между двумя типами данных|Создает исключение <xref:System.InvalidCastException>|  
|`DirectCast`|Типы данных|Один тип должен наследовать или реализовывать другой|Создает исключение <xref:System.InvalidCastException>|  
|[Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Только ссылочные типы|Один тип должен наследовать или реализовывать другой|Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Пример  
 В следующем примере показано два способа использования `DirectCast`, завершается ошибкой во время выполнения и один, завершается успешно.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 В предыдущем примере тип времени выполнения `q` — `Double`. `CType` завершается успешно, поскольку `Double` можно преобразовать в `Integer`. Однако первый `DirectCast` завершается ошибкой во время выполнения, поскольку тип времени выполнения `Double` не имеет отношения наследования с `Integer`, даже если существует преобразование. Второй `DirectCast` завершается успешно, поскольку он преобразует типа <xref:System.Windows.Forms.Form> ввода <xref:System.Windows.Forms.Control>, из которого <xref:System.Windows.Forms.Form> наследует.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
