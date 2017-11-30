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
# <a name="protected-internal-c-reference"></a><span data-ttu-id="b17bd-102">защищенные внутренние (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b17bd-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="b17bd-103">`protected internal` Сочетание ключевых слов — это модификатор доступа члена.</span><span class="sxs-lookup"><span data-stu-id="b17bd-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="b17bd-104">Защищенного внутреннего члена доступен из текущей сборки или типы, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="b17bd-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="b17bd-105">Сравнение модификатора `protected internal` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b17bd-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="b17bd-106">Пример</span><span class="sxs-lookup"><span data-stu-id="b17bd-106">Example</span></span>  
 <span data-ttu-id="b17bd-107">Защищенного внутреннего члена базового класса доступен из любого типа в пределах содержащего сборки.</span><span class="sxs-lookup"><span data-stu-id="b17bd-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="b17bd-108">Она также доступна в производном классе, расположенный в другой сборке, только в том случае, если доступ осуществляется через переменную типа производного класса.</span><span class="sxs-lookup"><span data-stu-id="b17bd-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="b17bd-109">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="b17bd-109">For example, consider the following code segment:</span></span>  

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
 <span data-ttu-id="b17bd-110">Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="b17bd-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="b17bd-111">Первый файл содержит открытый базовый класс `BaseClass`и еще один класс `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="b17bd-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="b17bd-112">`BaseClass`владеет защищенного внутреннего члена `myValue`, который осуществляется `TestAccess` типа.</span><span class="sxs-lookup"><span data-stu-id="b17bd-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="b17bd-113">Во втором файле попытка получить доступ к `myValue` через экземпляр `BaseClass` приведет к ошибке во время доступа к этому члену через экземпляр производного класса `DerivedClass` будет выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="b17bd-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="b17bd-114">Члены структуры не могут быть `protected internal` , так как структуры не наследуется.</span><span class="sxs-lookup"><span data-stu-id="b17bd-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b17bd-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b17bd-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b17bd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b17bd-116">See Also</span></span>  
 <span data-ttu-id="b17bd-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b17bd-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b17bd-119">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b17bd-120">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="b17bd-121">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="b17bd-122">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="b17bd-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="b17bd-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="b17bd-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="b17bd-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="b17bd-126">[Вопросы безопасности для ключевых слов internal virtual](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="b17bd-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
