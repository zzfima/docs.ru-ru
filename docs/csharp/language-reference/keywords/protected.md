---
title: protected (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 18278ed28f899d9030d6056eca9bbe83ebec04c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="protected-c-reference"></a>protected (справочник по C#)
Ключевое слово `protected` является модификатором доступа к члену. 

 > Эта страница содержит `protected` доступа. `protected` Также ключевое слово является частью [ `protected internal` ](./protected-internal.md) и [ `private protected` ](./private-protected.md) модификаторы доступа. 

Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов. 

Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md). 
  
## <a name="example"></a>Пример  
 Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса. Для примера рассмотрим следующий сегмент кода:  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.  
  
 Элементы структуры защитить нельзя, поскольку структура не может наследоваться.  
  
## <a name="example"></a>Пример  
 В этом примере класс `DerivedPoint` является производным от класса `Point`. В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 Если изменить уровни доступа `x` и `y` на [private](../../../csharp/language-reference/keywords/private.md), компилятор выдаст сообщения об ошибках:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 [Вопросы безопасности для ключевых слов internal virtual](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))