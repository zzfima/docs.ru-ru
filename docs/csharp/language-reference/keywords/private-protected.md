---
title: private protected (справочник по C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 0d511f55f44511590fbe92a98cef118e0cb482e2
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457255"
---
# <a name="private-protected-c-reference"></a>private protected (справочник по C#)
Комбинация ключевых слов `private protected` является модификатором доступа к члену. К члену private protected имеют доступ типы, производные от содержащего класса, но только в пределах содержащей сборки. Сравнение модификатора `private protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md). 

> [!NOTE]
> Модификатор доступа `private protected` допустим в C# 7.2 и более поздних версий.
   
## <a name="example"></a>Пример  
 Член базового класса private protected доступен из производных типов в содержащей сборке только в том случае, если статический тип переменной является типом производного класса. Для примера рассмотрим следующий сегмент кода:  
  
 ```csharp
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
  
```csharp  
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
 Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`. Первый файл содержит открытый базовый класс, `BaseClass`, и производный от него тип, `DerivedClass1`. `BaseClass` владеет членом private protected, `myValue`, к которому `DerivedClass1` пытается получить доступ двумя способами. Первая попытка доступа к `myValue` через экземпляр `BaseClass` приведет к ошибке. Однако попытка использовать его в качестве наследуемого члена в `DerivedClass1` завершится успешно.
Во втором файле попытка получить доступ к `myValue` в качестве наследуемого члена `DerivedClass2` приведет к ошибке, поскольку он доступен только для производных типов в Assembly1. 

 Элементы структуры не могут иметь модификатор `private protected`, поскольку структура не может наследоваться.  
  
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
