---
title: Оператор TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 53306575cfc385039be3939fd87cf993b4509af4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348215"
---
# <a name="trycast-operator-visual-basic"></a>Оператор TryCast (Visual Basic)
Вводит операцию преобразования типа, которая не создает исключение.  
  
## <a name="remarks"></a>Примечания  
 Если попытка преобразования завершается неудачно, `CType` и `DirectCast` вызывают ошибку <xref:System.InvalidCastException>. Это может негативно сказаться на производительности приложения. `TryCast` [ничего не](../../../visual-basic/language-reference/nothing.md)возвращает, поэтому вместо того, чтобы выполнять обработку возможного исключения, требуется только проверить возвращаемый результат для `Nothing`.  
  
 Ключевое слово `TryCast` используется точно так же, как при использовании [функции CType](../../../visual-basic/language-reference/functions/ctype-function.md) и ключевого слова [оператора DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) . Укажите выражение в качестве первого аргумента и тип, чтобы преобразовать его в качестве второго аргумента. `TryCast` работает только с ссылочными типами, такими как классы и интерфейсы. Для этого требуется отношение наследования или реализации между двумя типами. Это означает, что один тип должен наследовать или реализовывать другой.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `TryCast` создает ошибку компилятора, если обнаруживается, что связь наследования или реализации не существует. Но отсутствие ошибки компилятора не гарантирует успешного преобразования. Если требуемое преобразование является узким, оно может привести к сбою во время выполнения. Если это происходит, `TryCast` [ничего не](../../../visual-basic/language-reference/nothing.md)возвращает.  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Ниже приведены сравнения ключевых слов преобразования типов.  
  
|Ключевое слово|Типы данных|Отношение аргумента|Сбой во время выполнения|  
|---|---|---|---|  
|[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)|Любые типы данных|Для двух типов данных должно быть определено расширяющее или суженное преобразование.|Создает исключение <xref:System.InvalidCastException>|  
|[Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|Любые типы данных|Один тип должен наследовать или реализовывать другой тип|Создает исключение <xref:System.InvalidCastException>|  
|`TryCast`|Только ссылочные типы|Один тип должен наследовать или реализовывать другой тип|[Ничего не](../../../visual-basic/language-reference/nothing.md) возвращает|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
