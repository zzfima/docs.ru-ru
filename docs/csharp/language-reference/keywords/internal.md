---
title: "internal (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
dev_langs:
- CSharp
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5674a78e2c317357c31d9e2661a25ce86cbf4f6a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="internal-c-reference"></a><span data-ttu-id="fa7fd-102">internal (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fa7fd-102">internal (C# Reference)</span></span>
<span data-ttu-id="fa7fd-103">Ключевое слово `internal` является [модификатором доступа](../../../csharp/language-reference/keywords/access-modifiers.md) для типов и членов типов.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> <span data-ttu-id="fa7fd-104">Внутренние типы или члены доступны только внутри файлов в той же сборке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fa7fd-104">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 <span data-ttu-id="fa7fd-105">Доступ к типам и членам, которые имеют модификатор доступа `protected internal`, может осуществляться из текущей сборки или типов, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-105">Types or members that have access modifier `protected internal` can be accessed from the current assembly or from types that are derived from the containing class.</span></span>  
  
 <span data-ttu-id="fa7fd-106">Сравнение модификатора `internal` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="fa7fd-106">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="fa7fd-107">Дополнительные сведения о сборках см. в разделе [Сборки и глобальный кэш сборок](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa7fd-107">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="fa7fd-108">Обычно доступ к внутренним компонентам используется в разработке на основе компонентов, так как он позволяет группе компонентов взаимодействовать в закрытой форме, без их предоставления остальной части кода приложения.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-108">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="fa7fd-109">Например, платформа для создания графических интерфейсов пользователя может предоставлять классы `Control` и `Form`, взаимодействующие с помощью членов с внутренним доступом.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-109">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="fa7fd-110">Поскольку эти члены являются внутренними, они не предоставляются коду, использующему платформу.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-110">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="fa7fd-111">Будет ошибкой ссылаться на тип или член с внутренним доступом из-за пределов сборки, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-111">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7fd-112">Пример</span><span class="sxs-lookup"><span data-stu-id="fa7fd-112">Example</span></span>  
 <span data-ttu-id="fa7fd-113">Этот пример содержит два файла, `Assembly1.cs` и `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-113">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="fa7fd-114">Первый файл содержит внутренний базовый класс `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-114">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="fa7fd-115">Во втором файле попытка создать экземпляр `BaseClass` приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-115">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="fa7fd-116">Пример</span><span class="sxs-lookup"><span data-stu-id="fa7fd-116">Example</span></span>  
 <span data-ttu-id="fa7fd-117">В этом примере используйте те же файлы, которые использовались в примере 1, однако измените уровень доступности `BaseClass` на `public`.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-117">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="fa7fd-118">Кроме того, измените уровень доступности члена `IntM` на `internal`.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-118">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="fa7fd-119">В этом случае можно создать экземпляр класса, но нельзя получить доступ к внутреннему члену.</span><span class="sxs-lookup"><span data-stu-id="fa7fd-119">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="fa7fd-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fa7fd-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa7fd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fa7fd-121">See Also</span></span>  
 <span data-ttu-id="fa7fd-122">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fa7fd-123">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fa7fd-124">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fa7fd-125">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-125">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="fa7fd-126">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-126">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="fa7fd-127">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="fa7fd-128">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-128">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="fa7fd-129">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="fa7fd-129">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="fa7fd-130">protected</span><span class="sxs-lookup"><span data-stu-id="fa7fd-130">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)

