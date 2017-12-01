---
title: "Private, protected (Справочник по C#)"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a>Private, protected (Справочник по C#)
`private protected` Сочетание ключевых слов — это модификатор доступа члена. Защищенный закрытый член имеет доступ по типам, производным от содержащего класса, но только в пределах содержащего сборки. Сравнение модификатора `private protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Пример  
 Закрытый защищенный член базового класса доступно из производных типов в его сборке, содержащей только в том случае, если статический тип переменной является тип производного класса. Для примера рассмотрим следующий сегмент кода:  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`. Первый файл содержит открытый базовый класс `BaseClass`и тип, производный от него, `DerivedClass1`. `BaseClass`защищенный закрытый член, которому принадлежит `myValue`, который `DerivedClass1` пытается получить доступ к одним из двух способов. Первая попытка доступа к `myValue` через экземпляр `BaseClass` приведет к ошибке. Однако попытка использовать ее в качестве наследуемого члена в `DerivedClass1` будет выполнена успешно.
Во втором файле попытка получить доступ к `myValue` наследуемого члена из `DerivedClass2` приведет к ошибке, как оно доступно только для производных типов в Assembly1. 

 Члены структуры не могут быть `private protected` , так как структуры не наследуется.  
  
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
