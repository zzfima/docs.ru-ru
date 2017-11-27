---
title: "Оператор TryCast (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords: TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a>Оператор TryCast (Visual Basic)
Вводит операцию преобразования типа, не вызывает исключение.  
  
## <a name="remarks"></a>Примечания  
 Если попытка преобразования завершается ошибкой, `CType` и `DirectCast` оба throw <xref:System.InvalidCastException> ошибки. Это может отрицательно сказаться на производительности приложения. `TryCast`Возвращает [ничего](../../../visual-basic/language-reference/nothing.md)таким образом, вместо того, для обработки возможных исключений, требуется только протестировать возвращенный результат от `Nothing`.  
  
 Вы используете `TryCast` ключевое слово так же, как [функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) ключевое слово. Можно указать выражение в качестве первого аргумента и тип для преобразования его в качестве второго аргумента. `TryCast`работает только со ссылочными типами, таких как классы и интерфейсы. Требуется отношение наследования или реализации между двумя типами. Это означает, что один тип должен реализовывать или наследовать из другого.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `TryCast`создает ошибку компилятора, если он обнаруживает, что существует отношение наследования или реализации. Однако отсутствие ошибки компилятора не гарантирует успешное преобразование. Если требуемое преобразование будет сужающим, то возможен сбой во время выполнения. В этом случае `TryCast` возвращает [ничего не](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Сравнение ключевых слов преобразования типов выглядит следующим образом.  
  
|Ключевое слово|Типы данных|Отношение аргументов|Ошибка времени выполнения|  
|---|---|---|---|  
|[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Типы данных|Должен быть определен расширяющее или сужающее преобразование между двумя типами данных|Создает исключение<xref:System.InvalidCastException>|  
|[Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|Типы данных|Один тип должен наследовать или реализовывать другой|Создает исключение<xref:System.InvalidCastException>|  
|`TryCast`|Только ссылочные типы|Один тип должен наследовать или реализовывать другой|Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
