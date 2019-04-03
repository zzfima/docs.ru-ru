---
title: Оператор DirectCast (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 628ce4f06b91d0f514f71dea3aad8ea0fee6dccf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821508"
---
# <a name="directcast-operator-visual-basic"></a>Оператор DirectCast (Visual Basic)
Вводит операцию преобразования типа, на основе наследования или реализации.  
  
## <a name="remarks"></a>Примечания  
 `DirectCast` не используйте подпрограммы поддержки времени выполнения для преобразования, поэтому она обеспечивает немного лучшую производительность, чем Visual Basic `CType` при преобразовании из типа данных `Object`.  
  
 Использовании `DirectCast` аналогично тому, как можно использовать ключевое слово [функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) ключевое слово. Необходимо указать в качестве первого аргумента и тип для преобразования его в качестве второго аргумента выражение. `DirectCast` требуется отношение наследования или реализации между типами данных обоих аргументов. Это означает, что один тип должен наследовать или реализовывать другой.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `DirectCast` создает ошибку компилятора, если она обнаруживает, что существует отсутствует отношение наследования или реализации. Но отсутствие ошибки компилятора не гарантирует успешное преобразование. Если нужное преобразование является сужающим, во время выполнения может завершиться ошибкой. В этом случае среда выполнения создает <xref:System.InvalidCastException> ошибки.  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Сравнение ключевых слов преобразования типов выглядит следующим образом.  
  
|Ключевое слово|Типы данных|Связь аргументов|Ошибка времени выполнения|  
|---|---|---|---|  
|[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Типы данных|Расширяющее или сужающее преобразование должен быть определен между двумя типами данных|Создает исключение <xref:System.InvalidCastException>|  
|`DirectCast`|Типы данных|Один тип должен наследовать или реализации другого типа|Создает исключение <xref:System.InvalidCastException>|  
|[Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Только ссылочные типы|Один тип должен наследовать или реализации другого типа|Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Пример  
 В следующем примере показано два способа использования `DirectCast`, который не во время выполнения и один, завершается успешно.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 В предыдущем примере, тип времени выполнения `q` является `Double`. `CType` завершается успешно, поскольку `Double` может быть преобразован в `Integer`. Тем не менее первый `DirectCast` завершается ошибкой во время выполнения, так как тип времени выполнения `Double` не имеет отношения наследования с `Integer`, несмотря на то, что существует преобразование. Второй `DirectCast` завершается успешно, поскольку преобразование из типа <xref:System.Windows.Forms.Form> ввода <xref:System.Windows.Forms.Control>, из которого <xref:System.Windows.Forms.Form> наследует.  
  
## <a name="see-also"></a>См. также

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
