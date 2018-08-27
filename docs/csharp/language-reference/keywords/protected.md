---
title: protected (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: 2da8211ac21a5016478e7b881e7f2f9925b49cef
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001338"
---
# <a name="protected-c-reference"></a><span data-ttu-id="750c6-102">protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="750c6-102">protected (C# Reference)</span></span>
<span data-ttu-id="750c6-103">Ключевое слово `protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="750c6-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="750c6-104">Эта страница содержит доступ `protected`.</span><span class="sxs-lookup"><span data-stu-id="750c6-104">This page covers `protected` access.</span></span> <span data-ttu-id="750c6-105">Ключевое слово `protected` также является частью модификаторов доступа [`protected internal`](./protected-internal.md) и [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="750c6-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="750c6-106">Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.</span><span class="sxs-lookup"><span data-stu-id="750c6-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="750c6-107">Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="750c6-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="750c6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="750c6-108">Example</span></span>  
 <span data-ttu-id="750c6-109">Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="750c6-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="750c6-110">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="750c6-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="750c6-111">Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.</span><span class="sxs-lookup"><span data-stu-id="750c6-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="750c6-112">Элементы структуры защитить нельзя, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="750c6-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="750c6-113">Пример</span><span class="sxs-lookup"><span data-stu-id="750c6-113">Example</span></span>  
 <span data-ttu-id="750c6-114">В этом примере класс `DerivedPoint` является производным от класса `Point`.</span><span class="sxs-lookup"><span data-stu-id="750c6-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="750c6-115">В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.</span><span class="sxs-lookup"><span data-stu-id="750c6-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="750c6-116">Если изменить уровни доступа `x` и `y` на [private](../../../csharp/language-reference/keywords/private.md), компилятор выдаст сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="750c6-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="750c6-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="750c6-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## 

- [<span data-ttu-id="750c6-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="750c6-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="750c6-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="750c6-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="750c6-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="750c6-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="750c6-121">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="750c6-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="750c6-122">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="750c6-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="750c6-123">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="750c6-123">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="750c6-124">public</span><span class="sxs-lookup"><span data-stu-id="750c6-124">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
- [<span data-ttu-id="750c6-125">private</span><span class="sxs-lookup"><span data-stu-id="750c6-125">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="750c6-126">internal</span><span class="sxs-lookup"><span data-stu-id="750c6-126">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
- <span data-ttu-id="750c6-127">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="750c6-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>