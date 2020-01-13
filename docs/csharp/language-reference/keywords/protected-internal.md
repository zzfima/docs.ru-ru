---
title: protected internal. Справочник по C#
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 877df74b51fb859043171619f5687ecddb8409d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713200"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="ab100-102">protected internal (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ab100-102">protected internal (C# Reference)</span></span>

<span data-ttu-id="ab100-103">Комбинация ключевых слов `protected internal` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="ab100-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="ab100-104">Доступ к членам с модификатором доступа protected internal может осуществляться из текущей сборки или типов, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="ab100-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="ab100-105">Сравнение модификатора `protected internal` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ab100-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="ab100-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ab100-106">Example</span></span>

<span data-ttu-id="ab100-107">Член базового класса с модификатором доступа protected internal доступен из любого типа в пределах содержащей сборки.</span><span class="sxs-lookup"><span data-stu-id="ab100-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="ab100-108">Он также доступен в производном классе, расположенном в другой сборке, только в том случае, если доступ осуществляется через переменную типа производного класса.</span><span class="sxs-lookup"><span data-stu-id="ab100-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="ab100-109">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="ab100-109">For example, consider the following code segment:</span></span>

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
        var baseObject = new BaseClass();
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
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="ab100-110">Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="ab100-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="ab100-111">Первый файл содержит открытый базовый класс, `BaseClass`, и еще один класс, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="ab100-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="ab100-112">`BaseClass` владеет членом protected internal, `myValue`, доступ к которому осуществляется типом `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="ab100-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="ab100-113">Во втором файле попытка получить доступ к `myValue` через экземпляр `BaseClass` приведет к ошибке во время доступа к этому члену через экземпляр производного класса. `DerivedClass` гарантирует успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="ab100-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="ab100-114">Элементы структуры не могут иметь модификатор `protected internal`, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="ab100-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ab100-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ab100-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ab100-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ab100-116">See also</span></span>

- [<span data-ttu-id="ab100-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ab100-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ab100-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ab100-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ab100-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ab100-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ab100-120">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="ab100-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="ab100-121">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="ab100-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="ab100-122">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="ab100-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="ab100-123">public</span><span class="sxs-lookup"><span data-stu-id="ab100-123">public</span></span>](public.md)
- [<span data-ttu-id="ab100-124">private</span><span class="sxs-lookup"><span data-stu-id="ab100-124">private</span></span>](private.md)
- [<span data-ttu-id="ab100-125">internal</span><span class="sxs-lookup"><span data-stu-id="ab100-125">internal</span></span>](internal.md)
- <span data-ttu-id="ab100-126">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ab100-126">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
