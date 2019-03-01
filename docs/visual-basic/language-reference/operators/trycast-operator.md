---
title: Оператор TryCast (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dd50a23f09fa5dd49b86eefe163cea20430e2360
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981287"
---
# <a name="trycast-operator-visual-basic"></a>Оператор TryCast (Visual Basic)
Вводит операцию преобразования типа, который выдает исключение.  
  
## <a name="remarks"></a>Примечания  
 Если попытка преобразования не, `CType` и `DirectCast` оба throw <xref:System.InvalidCastException> ошибки. Это может отрицательно повлиять на производительность приложения. `TryCast` Возвращает [ничего не](../../../visual-basic/language-reference/nothing.md), что вместо того, для обработки возможных исключений, должны только проверять возвращаемый результат с `Nothing`.  
  
 Использовании `TryCast` так же, используется ключевое слово [функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) ключевое слово. Необходимо указать в качестве первого аргумента и тип для преобразования его в качестве второго аргумента выражение. `TryCast` работает только со ссылочными типами, такими как классы и интерфейсы. Он требует отношение наследования или реализации между двумя типами. Это означает, что один тип должен наследовать или реализовывать другой.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `TryCast` создает ошибку компилятора, если она обнаруживает, что существует отсутствует отношение наследования или реализации. Но отсутствие ошибки компилятора не гарантирует успешное преобразование. Если нужное преобразование является сужающим, во время выполнения может завершиться ошибкой. В этом случае `TryCast` возвращает [ничего не](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Сравнение ключевых слов преобразования типов выглядит следующим образом.  
  
|Ключевое слово|Типы данных|Связь аргументов|Ошибка времени выполнения|  
|---|---|---|---|  
|[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Типы данных|Расширяющее или сужающее преобразование должен быть определен между двумя типами данных|Создает исключение <xref:System.InvalidCastException>|  
|[Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|Типы данных|Один тип должен наследовать или реализации другого типа|Создает исключение <xref:System.InvalidCastException>|  
|`TryCast`|Только ссылочные типы|Один тип должен наследовать или реализации другого типа|Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
