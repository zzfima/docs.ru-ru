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
# <a name="private-protected-c-reference"></a><span data-ttu-id="a145c-102">Private, protected (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a145c-102">private protected (C# Reference)</span></span>
<span data-ttu-id="a145c-103">`private protected` Сочетание ключевых слов — это модификатор доступа члена.</span><span class="sxs-lookup"><span data-stu-id="a145c-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a145c-104">Защищенный закрытый член имеет доступ по типам, производным от содержащего класса, но только в пределах содержащего сборки.</span><span class="sxs-lookup"><span data-stu-id="a145c-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="a145c-105">Сравнение модификатора `private protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a145c-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="a145c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a145c-106">Example</span></span>  
 <span data-ttu-id="a145c-107">Закрытый защищенный член базового класса доступно из производных типов в его сборке, содержащей только в том случае, если статический тип переменной является тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="a145c-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="a145c-108">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="a145c-108">For example, consider the following code segment:</span></span>  
  
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
 <span data-ttu-id="a145c-109">Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="a145c-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="a145c-110">Первый файл содержит открытый базовый класс `BaseClass`и тип, производный от него, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="a145c-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="a145c-111">`BaseClass`защищенный закрытый член, которому принадлежит `myValue`, который `DerivedClass1` пытается получить доступ к одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="a145c-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="a145c-112">Первая попытка доступа к `myValue` через экземпляр `BaseClass` приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="a145c-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="a145c-113">Однако попытка использовать ее в качестве наследуемого члена в `DerivedClass1` будет выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a145c-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="a145c-114">Во втором файле попытка получить доступ к `myValue` наследуемого члена из `DerivedClass2` приведет к ошибке, как оно доступно только для производных типов в Assembly1.</span><span class="sxs-lookup"><span data-stu-id="a145c-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="a145c-115">Члены структуры не могут быть `private protected` , так как структуры не наследуется.</span><span class="sxs-lookup"><span data-stu-id="a145c-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a145c-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a145c-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a145c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a145c-117">See Also</span></span>  
 <span data-ttu-id="a145c-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a145c-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a145c-120">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a145c-121">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="a145c-122">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="a145c-123">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="a145c-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="a145c-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="a145c-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="a145c-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="a145c-127">[Вопросы безопасности для ключевых слов internal virtual](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="a145c-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
