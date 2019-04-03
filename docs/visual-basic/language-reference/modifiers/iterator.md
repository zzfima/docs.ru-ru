---
title: Итератор (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 499949d1f4c20e1f465355bd076ba39f1496779b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822704"
---
# <a name="iterator-visual-basic"></a>Итератор (Visual Basic)
Указывает, что функция или `Get` метод доступа является итератором.  
  
## <a name="remarks"></a>Примечания  
 *Итератор* выполняет настраиваемую итерацию по коллекции. Итератор использует [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) инструкцию для возврата всех элементов в коллекции по одному за раз. Когда `Yield` к оператору, текущее расположение в коде сохраняется. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Итератор, который можно реализовать как функции или как `Get` доступа определения свойства. `Iterator` Отображается модификатор в объявлении функции итератора или `Get` метода доступа.  
  
 Итератор вызывается из клиентского кода с помощью [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Тип возвращаемого значения функции итератора или `Get` метод доступа может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Итератор не может содержать `ByRef` параметров.  
  
 Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Итератор, который может быть анонимной функции. Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Использование  
 Модификатор `Iterator` можно использовать в следующих контекстах:  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Пример  
 Ниже приведен пример функции итератора. Имеет функции итератора `Yield` инструкцию, которая находится внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. Каждая итерация [для каждого](../../../visual-basic/language-reference/statements/for-each-next-statement.md) тела оператора в `Main` создает вызов `Power` функции итератора. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. `Iterator` Является модификатор в объявлении свойства.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Итераторы](../../programming-guide/concepts/iterators.md)
- [Оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
