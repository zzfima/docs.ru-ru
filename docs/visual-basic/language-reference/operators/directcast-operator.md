---
title: Оператор DirectCast
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331306"
---
# <a name="directcast-operator-visual-basic"></a>Оператор DirectCast (Visual Basic)
Вводит операцию преобразования типов на основе наследования или реализации.  
  
## <a name="remarks"></a>Примечания  
 `DirectCast` не Visual Basic использует вспомогательные подпрограммы времени выполнения для преобразования, поэтому он может обеспечить более высокую производительность, чем `CType` при преобразовании в `Object`типа данных и из него.  
  
 Используйте ключевое слово `DirectCast`, как и при использовании [функции CType](../../../visual-basic/language-reference/functions/ctype-function.md) и ключевого слова [оператора TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) . Укажите выражение в качестве первого аргумента и тип, чтобы преобразовать его в качестве второго аргумента. для `DirectCast` требуется связь наследования или реализации между типами данных двух аргументов. Это означает, что один тип должен наследовать или реализовывать другой.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `DirectCast` создает ошибку компилятора, если обнаруживается, что связь наследования или реализации не существует. Но отсутствие ошибки компилятора не гарантирует успешного преобразования. Если требуемое преобразование является узким, оно может привести к сбою во время выполнения. Если это происходит, среда выполнения вызывает ошибку <xref:System.InvalidCastException>.  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Ниже приведены сравнения ключевых слов преобразования типов.  
  
|Ключевое слово|Типы данных|Отношение аргумента|Сбой во время выполнения|  
|---|---|---|---|  
|[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)|Любые типы данных|Для двух типов данных должно быть определено расширяющее или суженное преобразование.|Создает исключение <xref:System.InvalidCastException>|  
|`DirectCast`|Любые типы данных|Один тип должен наследовать или реализовывать другой тип|Создает исключение <xref:System.InvalidCastException>|  
|[Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Только ссылочные типы|Один тип должен наследовать или реализовывать другой тип|[Ничего не](../../../visual-basic/language-reference/nothing.md) возвращает|  
  
## <a name="example"></a>Пример  
 В следующем примере показаны два применения `DirectCast`, один из которых завершается сбоем во время выполнения и один из которых завершается успешно.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 В предыдущем примере тип времени выполнения `q` `Double`. `CType` выполнен, так как `Double` можно преобразовать в `Integer`. Однако первый `DirectCast` завершается ошибкой во время выполнения, так как тип времени выполнения `Double` не имеет связи наследования с `Integer`, даже если существует преобразование. Второй `DirectCast` будет выполнен, так как он преобразует из типа <xref:System.Windows.Forms.Form> в тип <xref:System.Windows.Forms.Control>, из которого <xref:System.Windows.Forms.Form> наследуется.  
  
## <a name="see-also"></a>См. также

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
