---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351526"
---
# <a name="iterator-visual-basic"></a>Итератор (Visual Basic)
Указывает, что функция или метод доступа `Get` являются итератором.  
  
## <a name="remarks"></a>Заметки  
 *Итератор* выполняет настраиваемую итерацию по коллекции. Итератор использует оператор [yield](../../../visual-basic/language-reference/statements/yield-statement.md) для возвращения каждого элемента в коллекции по одному за раз. При достижении оператора `Yield` текущее место в коде сохраняется. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Итератор может быть реализован как функция или как метод доступа `Get` для определения свойства. Модификатор `Iterator` отображается в объявлении функции итератора или методе доступа `Get`.  
  
 Итератор вызывается из клиентского кода с помощью метода [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Тип возвращаемого значения функции итератора или метода доступа `Get` может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>или <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Итератор не может иметь никаких `ByRef` параметров.  
  
 Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Итератор может быть анонимной функцией. Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Использование  
 Модификатор `Iterator` можно использовать в следующих контекстах:  
  
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется функция итератора. Функция итератора содержит оператор `Yield`, который находится внутри блока [for... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл. Каждая итерация тела оператора [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в `Main` создает вызов функции итератора `Power`. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. Модификатор `Iterator` находится в объявлении свойства.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Итераторы](../../programming-guide/concepts/iterators.md)
- [Оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
