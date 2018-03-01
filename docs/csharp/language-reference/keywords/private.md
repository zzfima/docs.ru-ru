---
title: "private (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9cc8f86166888b47a758e200182d319c68ca6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="private-c-reference"></a>private (Справочник по C#)
Ключевое слово `private` является модификатором доступа к члену. 
   
 > Эта страница содержит `private` доступа. `private` Также ключевое слово является частью [ `private protected` ](./private-protected.md) модификатор доступа.
  
Закрытый доступ является уровнем доступа с минимальными правами. Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 Вложенные типы в том же теле могут также обращаться к таким закрытым членам.  
  
 Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.  
  
 Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## <a name="example"></a>Пример  
 В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`. Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов. Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`. Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения. (Дополнительные сведения см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).)  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
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
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
