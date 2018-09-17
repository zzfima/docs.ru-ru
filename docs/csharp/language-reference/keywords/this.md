---
title: this (Справочник по C#)
description: Ключевое слово this (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: df1bf6a3e6d24b231bf5e3c7a960f49084c4e53a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45616582"
---
# <a name="this-c-reference"></a><span data-ttu-id="5dce4-103">this (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5dce4-103">this (C# Reference)</span></span>
<span data-ttu-id="5dce4-104">Ключевое слово `this` ссылается на текущий экземпляр класса, а также используется в качестве модификатора первого параметра метода расширения.</span><span class="sxs-lookup"><span data-stu-id="5dce4-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dce4-105">В этой статье рассматривается использование `this` с экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="5dce4-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="5dce4-106">Дополнительные сведения об использовании этого ключевого слова в методах расширения см. в разделе [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5dce4-106">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="5dce4-107">Ниже перечислены наиболее частые способы использования `this`.</span><span class="sxs-lookup"><span data-stu-id="5dce4-107">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="5dce4-108">Для квалификации элементов, скрытых одинаковыми именами, например:</span><span class="sxs-lookup"><span data-stu-id="5dce4-108">To qualify members hidden by similar names, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   <span data-ttu-id="5dce4-109">Для передачи другим методам объекта в качестве параметра, например:</span><span class="sxs-lookup"><span data-stu-id="5dce4-109">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```csharp  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="5dce4-110">Для объявления индексаторов, например:</span><span class="sxs-lookup"><span data-stu-id="5dce4-110">To declare indexers, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 <span data-ttu-id="5dce4-111">У статических функций-членов нет указателя `this`, так как они существуют только на уровне класса и не являются частями объектов.</span><span class="sxs-lookup"><span data-stu-id="5dce4-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="5dce4-112">Использование ссылки на `this` в статическом методе является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="5dce4-112">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dce4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5dce4-113">Example</span></span>  
 <span data-ttu-id="5dce4-114">В этом примере `this` используется для квалификации членов класса `Employee`, `name` и `alias`, которые скрыты одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="5dce4-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="5dce4-115">Это ключевое слово также используется для передачи объекта в метод `CalcTax`, который принадлежит другому классу.</span><span class="sxs-lookup"><span data-stu-id="5dce4-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5dce4-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5dce4-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5dce4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5dce4-117">See Also</span></span>

- [<span data-ttu-id="5dce4-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5dce4-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5dce4-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5dce4-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5dce4-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="5dce4-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="5dce4-121">base</span><span class="sxs-lookup"><span data-stu-id="5dce4-121">base</span></span>](../../../csharp/language-reference/keywords/base.md)  
- [<span data-ttu-id="5dce4-122">Методы</span><span class="sxs-lookup"><span data-stu-id="5dce4-122">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
