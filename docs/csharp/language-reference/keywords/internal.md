---
title: "internal (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords: internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a3b115022ed2b38dfcfbbfad3c5fc00e0203b255
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="internal-c-reference"></a><span data-ttu-id="899c4-102">internal (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="899c4-102">internal (C# Reference)</span></span>
<span data-ttu-id="899c4-103">Ключевое слово `internal` является [модификатором доступа](../../../csharp/language-reference/keywords/access-modifiers.md) для типов и членов типов.</span><span class="sxs-lookup"><span data-stu-id="899c4-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="899c4-104">Эта страница содержит `internal` доступа.</span><span class="sxs-lookup"><span data-stu-id="899c4-104">This page covers `internal` access.</span></span> <span data-ttu-id="899c4-105">`internal` Также ключевое слово является частью [ `protected internal` ](./protected-internal.md) модификатор доступа.</span><span class="sxs-lookup"><span data-stu-id="899c4-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="899c4-106">Внутренние типы или члены доступны только внутри файлов в той же сборке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="899c4-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="899c4-107">Сравнение модификатора `internal` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="899c4-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="899c4-108">Дополнительные сведения о сборках см. в разделе [Сборки и глобальный кэш сборок](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="899c4-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="899c4-109">Обычно доступ к внутренним компонентам используется в разработке на основе компонентов, так как он позволяет группе компонентов взаимодействовать в закрытой форме, без их предоставления остальной части кода приложения.</span><span class="sxs-lookup"><span data-stu-id="899c4-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="899c4-110">Например, платформа для создания графических интерфейсов пользователя может предоставлять классы `Control` и `Form`, взаимодействующие с помощью членов с внутренним доступом.</span><span class="sxs-lookup"><span data-stu-id="899c4-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="899c4-111">Поскольку эти члены являются внутренними, они не предоставляются коду, использующему платформу.</span><span class="sxs-lookup"><span data-stu-id="899c4-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="899c4-112">Будет ошибкой ссылаться на тип или член с внутренним доступом из-за пределов сборки, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="899c4-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="899c4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="899c4-113">Example</span></span>  
 <span data-ttu-id="899c4-114">Этот пример содержит два файла, `Assembly1.cs` и `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="899c4-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="899c4-115">Первый файл содержит внутренний базовый класс `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="899c4-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="899c4-116">Во втором файле попытка создать экземпляр `BaseClass` приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="899c4-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="899c4-117">Пример</span><span class="sxs-lookup"><span data-stu-id="899c4-117">Example</span></span>  
 <span data-ttu-id="899c4-118">В этом примере используйте те же файлы, которые использовались в примере 1, однако измените уровень доступности `BaseClass` на `public`.</span><span class="sxs-lookup"><span data-stu-id="899c4-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="899c4-119">Кроме того, измените уровень доступности члена `IntM` на `internal`.</span><span class="sxs-lookup"><span data-stu-id="899c4-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="899c4-120">В этом случае можно создать экземпляр класса, но нельзя получить доступ к внутреннему члену.</span><span class="sxs-lookup"><span data-stu-id="899c4-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="899c4-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="899c4-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="899c4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="899c4-122">See Also</span></span>  
 [<span data-ttu-id="899c4-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="899c4-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="899c4-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="899c4-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="899c4-125">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="899c4-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="899c4-126">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="899c4-126">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="899c4-127">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="899c4-127">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="899c4-128">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="899c4-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="899c4-129">public</span><span class="sxs-lookup"><span data-stu-id="899c4-129">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="899c4-130">private</span><span class="sxs-lookup"><span data-stu-id="899c4-130">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="899c4-131">protected</span><span class="sxs-lookup"><span data-stu-id="899c4-131">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
