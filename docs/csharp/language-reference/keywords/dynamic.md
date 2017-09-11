---
title: "dynamic (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- dynamic_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
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
ms.openlocfilehash: b68a6ef4dc3dda01638b9bb84db58ba77214f490
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="dynamic-c-reference"></a><span data-ttu-id="b64a3-102">dynamic (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b64a3-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="b64a3-103">Тип `dynamic` включает операции, в которых он применяется для обхода проверки типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b64a3-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="b64a3-104">Такие операции разрешаются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b64a3-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="b64a3-105">Тип `dynamic` упрощает доступ к API COM, таким как API автоматизации Office, а также к динамическим API, таким как библиотеки IronPython, и к HTML-модели DOM.</span><span class="sxs-lookup"><span data-stu-id="b64a3-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="b64a3-106">Тип `dynamic` в большинстве случаев ведет себя как тип `object`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="b64a3-107">При этом операции, содержащие выражения типа `dynamic`, не разрешаются или тип проверяется компилятором.</span><span class="sxs-lookup"><span data-stu-id="b64a3-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="b64a3-108">Компилятор объединяет сведения об операции, которые впоследствии будут использоваться для оценки этой операции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b64a3-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="b64a3-109">В рамках этого процесса переменные типа `dynamic` компилируются в переменные типа `object`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="b64a3-110">Таким образом, тип `dynamic` существует только во время компиляции, но не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b64a3-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="b64a3-111">В следующем примере переменной типа `dynamic` противопоставляется переменная типа `object`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="b64a3-112">Чтобы проверить тип каждой переменной во время компиляции, наведите указатель мыши на `dyn` или `obj` в операторах `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="b64a3-113">IntelliSense отображает **dynamic** для `dyn` и **object** для `obj`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 <span data-ttu-id="b64a3-114">[!code-cs[csrefKeywordsTypes 21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b64a3-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span></span>  
  
 <span data-ttu-id="b64a3-115">Операторы `WriteLine` отображают типы времени выполнения `dyn` и `obj`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-115">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="b64a3-116">На этом этапе оба имеют один и тот же тип — целое число.</span><span class="sxs-lookup"><span data-stu-id="b64a3-116">At that point, both have the same type, integer.</span></span> <span data-ttu-id="b64a3-117">Выводятся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="b64a3-117">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="b64a3-118">Чтобы увидеть разницу между `dyn` и `obj` во время компиляции, добавьте между объявлениями и операторами `WriteLine` в предыдущем примере следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="b64a3-118">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="b64a3-119">При попытке добавления целого числа и объекта в выражение `obj + 3` выдается ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="b64a3-119">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="b64a3-120">При этом для `dyn + 3` ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="b64a3-120">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="b64a3-121">Выражение, которое содержит `dyn`, не проверяется во время компиляции, поскольку тип `dyn` имеет значение `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="b64a3-121">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="b64a3-122">Контекст</span><span class="sxs-lookup"><span data-stu-id="b64a3-122">Context</span></span>  
 <span data-ttu-id="b64a3-123">В следующих ситуациях ключевое слово `dynamic` может отображаться как есть или как компонент сконструированного типа:</span><span class="sxs-lookup"><span data-stu-id="b64a3-123">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="b64a3-124">В объявлениях: как тип свойства, поля, индексатора, параметра возвращаемого значения, локальной переменной или ограничения типа.</span><span class="sxs-lookup"><span data-stu-id="b64a3-124">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="b64a3-125">В представленном ниже определении класса ключевое слово `dynamic` используется сразу в нескольких различных объявлениях.</span><span class="sxs-lookup"><span data-stu-id="b64a3-125">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     <span data-ttu-id="b64a3-126">[!code-cs[csrefKeywordsTypes #22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b64a3-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span></span>  
  
-   <span data-ttu-id="b64a3-127">В явных преобразованиях типа: как целевой тип преобразования.</span><span class="sxs-lookup"><span data-stu-id="b64a3-127">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     <span data-ttu-id="b64a3-128">[!code-cs[csrefKeywordsTypes #23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b64a3-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span></span>  
  
-   <span data-ttu-id="b64a3-129">В любом контексте, где типы служат в качестве значений, например справа от оператора `is` или `as`, либо в качестве аргумента для `typeof` в рамках сконструированного типа.</span><span class="sxs-lookup"><span data-stu-id="b64a3-129">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="b64a3-130">Например, ключевое слово `dynamic` можно использовать в следующих выражениях:</span><span class="sxs-lookup"><span data-stu-id="b64a3-130">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     <span data-ttu-id="b64a3-131">[!code-cs[csrefKeywordsTypes #24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b64a3-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b64a3-132">Пример</span><span class="sxs-lookup"><span data-stu-id="b64a3-132">Example</span></span>  
 <span data-ttu-id="b64a3-133">В следующем примере `dynamic` используется в нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="b64a3-133">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="b64a3-134">Метод `Main` также противопоставляет проверку типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b64a3-134">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 <span data-ttu-id="b64a3-135">[!code-cs[csrefKeywordsTypes #25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b64a3-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span></span>  
  
 <span data-ttu-id="b64a3-136">Дополнительные сведения и примеры см. в разделе [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="b64a3-136">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64a3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b64a3-137">See Also</span></span>  
 <span data-ttu-id="b64a3-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b64a3-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="b64a3-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b64a3-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="b64a3-140">[Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="b64a3-140">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="b64a3-141">[object](../../../csharp/language-reference/keywords/object.md) </span><span class="sxs-lookup"><span data-stu-id="b64a3-141">[object](../../../csharp/language-reference/keywords/object.md) </span></span>  
 <span data-ttu-id="b64a3-142">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="b64a3-142">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="b64a3-143">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="b64a3-143">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 <span data-ttu-id="b64a3-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="b64a3-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="b64a3-145">[Практическое руководство. Безопасное приведение с помощью операторов as и is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span><span class="sxs-lookup"><span data-stu-id="b64a3-145">[How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span></span>  
 [<span data-ttu-id="b64a3-146">Пошаговое руководство. Создание и использование динамических объектов</span><span class="sxs-lookup"><span data-stu-id="b64a3-146">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)

