---
title: Справочник по C#. Комбинация ключевых слов private protected
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: a73d61712075cf24d2b94c505104df1fade629e9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713213"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="0c124-102">private protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0c124-102">private protected (C# Reference)</span></span>

<span data-ttu-id="0c124-103">Комбинация ключевых слов `private protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="0c124-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="0c124-104">К члену private protected имеют доступ типы, производные от содержащего класса, но только в пределах содержащей сборки.</span><span class="sxs-lookup"><span data-stu-id="0c124-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="0c124-105">Сравнение модификатора `private protected` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0c124-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0c124-106">Модификатор доступа `private protected` допустим в C# 7.2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="0c124-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="0c124-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0c124-107">Example</span></span>

<span data-ttu-id="0c124-108">Член базового класса private protected доступен из производных типов в содержащей сборке только в том случае, если статический тип переменной является типом производного класса.</span><span class="sxs-lookup"><span data-stu-id="0c124-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="0c124-109">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="0c124-109">For example, consider the following code segment:</span></span>  

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
        var baseObject = new BaseClass();

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

<span data-ttu-id="0c124-110">Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="0c124-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="0c124-111">Первый файл содержит открытый базовый класс, `BaseClass`, и производный от него тип, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="0c124-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="0c124-112">`BaseClass` владеет членом private protected, `myValue`, к которому `DerivedClass1` пытается получить доступ двумя способами.</span><span class="sxs-lookup"><span data-stu-id="0c124-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="0c124-113">Первая попытка доступа к `myValue` через экземпляр `BaseClass` приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="0c124-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="0c124-114">Однако попытка использовать его в качестве наследуемого члена в `DerivedClass1` завершится успешно.</span><span class="sxs-lookup"><span data-stu-id="0c124-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="0c124-115">Во втором файле попытка получить доступ к `myValue` в качестве наследуемого члена `DerivedClass2` приведет к ошибке, поскольку он доступен только для производных типов в Assembly1.</span><span class="sxs-lookup"><span data-stu-id="0c124-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="0c124-116">Элементы структуры не могут иметь модификатор `private protected`, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="0c124-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="0c124-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0c124-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="0c124-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0c124-118">See also</span></span>

- [<span data-ttu-id="0c124-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0c124-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0c124-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0c124-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0c124-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0c124-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0c124-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="0c124-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="0c124-123">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="0c124-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="0c124-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="0c124-124">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0c124-125">public</span><span class="sxs-lookup"><span data-stu-id="0c124-125">public</span></span>](public.md)
- [<span data-ttu-id="0c124-126">private</span><span class="sxs-lookup"><span data-stu-id="0c124-126">private</span></span>](private.md)
- [<span data-ttu-id="0c124-127">internal</span><span class="sxs-lookup"><span data-stu-id="0c124-127">internal</span></span>](internal.md)
- <span data-ttu-id="0c124-128">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0c124-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
