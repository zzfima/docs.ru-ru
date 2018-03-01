---
title: "protected (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 18278ed28f899d9030d6056eca9bbe83ebec04c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="protected-c-reference"></a><span data-ttu-id="692d1-102">protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="692d1-102">protected (C# Reference)</span></span>
<span data-ttu-id="692d1-103">Ключевое слово `protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="692d1-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="692d1-104">Эта страница содержит `protected` доступа.</span><span class="sxs-lookup"><span data-stu-id="692d1-104">This page covers `protected` access.</span></span> <span data-ttu-id="692d1-105">`protected` Также ключевое слово является частью [ `protected internal` ](./protected-internal.md) и [ `private protected` ](./private-protected.md) модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="692d1-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="692d1-106">Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.</span><span class="sxs-lookup"><span data-stu-id="692d1-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="692d1-107">Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="692d1-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="692d1-108">Пример</span><span class="sxs-lookup"><span data-stu-id="692d1-108">Example</span></span>  
 <span data-ttu-id="692d1-109">Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="692d1-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="692d1-110">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="692d1-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="692d1-111">Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.</span><span class="sxs-lookup"><span data-stu-id="692d1-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="692d1-112">Элементы структуры защитить нельзя, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="692d1-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="692d1-113">Пример</span><span class="sxs-lookup"><span data-stu-id="692d1-113">Example</span></span>  
 <span data-ttu-id="692d1-114">В этом примере класс `DerivedPoint` является производным от класса `Point`.</span><span class="sxs-lookup"><span data-stu-id="692d1-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="692d1-115">В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.</span><span class="sxs-lookup"><span data-stu-id="692d1-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="692d1-116">Если изменить уровни доступа `x` и `y` на [private](../../../csharp/language-reference/keywords/private.md), компилятор выдаст сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="692d1-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="692d1-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="692d1-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="692d1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="692d1-118">See Also</span></span>  
 [<span data-ttu-id="692d1-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="692d1-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="692d1-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="692d1-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="692d1-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="692d1-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="692d1-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="692d1-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="692d1-123">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="692d1-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="692d1-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="692d1-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="692d1-125">public</span><span class="sxs-lookup"><span data-stu-id="692d1-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="692d1-126">private</span><span class="sxs-lookup"><span data-stu-id="692d1-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="692d1-127">internal</span><span class="sxs-lookup"><span data-stu-id="692d1-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="692d1-128">[Вопросы безопасности для ключевых слов internal virtual](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="692d1-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>