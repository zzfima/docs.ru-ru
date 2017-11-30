---
title: "защищенные внутренние (Справочник по C#)"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a>защищенные внутренние (Справочник по C#)
`protected internal` Сочетание ключевых слов — это модификатор доступа члена. Защищенного внутреннего члена доступен из текущей сборки или типы, которые являются производными от содержащего класса. Сравнение модификатора `protected internal` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Пример  
 Защищенного внутреннего члена базового класса доступен из любого типа в пределах содержащего сборки. Она также доступна в производном классе, расположенный в другой сборке, только в том случае, если доступ осуществляется через переменную типа производного класса. Для примера рассмотрим следующий сегмент кода:  

```
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`. Первый файл содержит открытый базовый класс `BaseClass`и еще один класс `TestAccess`. `BaseClass`владеет защищенного внутреннего члена `myValue`, который осуществляется `TestAccess` типа. Во втором файле попытка получить доступ к `myValue` через экземпляр `BaseClass` приведет к ошибке во время доступа к этому члену через экземпляр производного класса `DerivedClass` будет выполнена успешно. 

 Члены структуры не могут быть `protected internal` , так как структуры не наследуется.  
  
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
