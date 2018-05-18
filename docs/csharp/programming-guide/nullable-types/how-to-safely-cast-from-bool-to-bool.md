---
title: Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
ms.openlocfilehash: 18f44018621182427199dee56146f29b8d3068f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a>Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)
Тип `bool?`, допускающий значение NULL, может содержать три разных значения: `true`, `false` и `null`. Следовательно, тип `bool?` невозможно использовать в условных операторах, например с `if`, `for` или `while`. Так, следующий код вызовет ошибку компиляции.  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Это запрещено, так как непонятно, что означает `null` в контексте условного оператора. Чтобы использовать `bool?` в условном операторе, сначала проверьте свойство <xref:System.Nullable%601.HasValue%2A>, чтобы убедиться, что его значение не равно `null`, а затем приведите его к типу `bool`. Дополнительные сведения: [bool](../../../csharp/language-reference/keywords/bool.md). Если вы выполняете приведение для `bool?` со значением `null`, проверка условия создает исключение <xref:System.InvalidOperationException>. В следующем примере показан один из способов безопасного приведения из `bool?` к `bool`:  
  
## <a name="example"></a>Пример  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Буквенные ключевые слова](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
 [?? Оператор](../../../csharp/language-reference/operators/null-conditional-operator.md)
