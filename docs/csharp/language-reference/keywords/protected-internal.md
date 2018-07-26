---
title: protected internal (справочник по C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244862"
---
# <a name="protected-internal-c-reference"></a>protected internal (справочник по C#)
Комбинация ключевых слов `protected internal` является модификатором доступа к члену. Доступ к членам с модификатором доступа protected internal может осуществляться из текущей сборки или типов, которые являются производными от содержащего класса. Сравнение модификатора `protected internal` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Пример  
 Член базового класса с модификатором доступа protected internal доступен из любого типа в пределах содержащей сборки. Он также доступен в производном классе, расположенном в другой сборке, только в том случае, если доступ осуществляется через переменную типа производного класса. Для примера рассмотрим следующий сегмент кода:  

```csharp
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
  
```csharp  
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
 Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`. Первый файл содержит открытый базовый класс, `BaseClass`, и еще один класс, `TestAccess`. `BaseClass` владеет членом protected internal, `myValue`, доступ к которому осуществляется типом `TestAccess`. Во втором файле попытка получить доступ к `myValue` через экземпляр `BaseClass` приведет к ошибке во время доступа к этому члену через экземпляр производного класса. `DerivedClass` гарантирует успешное выполнение. 

 Элементы структуры не могут иметь модификатор `protected internal`, поскольку структура не может наследоваться.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
