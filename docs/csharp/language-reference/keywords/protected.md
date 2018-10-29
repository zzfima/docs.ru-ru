---
title: Ключевое слово protected (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: cc3c8f81edb68fb26be560c8635e30dfd6e7b372
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50183182"
---
# <a name="protected-c-reference"></a><span data-ttu-id="a7abb-102">protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a7abb-102">protected (C# Reference)</span></span>

<span data-ttu-id="a7abb-103">Ключевое слово `protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="a7abb-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="a7abb-104">Эта страница содержит доступ `protected`.</span><span class="sxs-lookup"><span data-stu-id="a7abb-104">This page covers `protected` access.</span></span> <span data-ttu-id="a7abb-105">Ключевое слово `protected` также является частью модификаторов доступа [`protected internal`](protected-internal.md) и [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="a7abb-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="a7abb-106">Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.</span><span class="sxs-lookup"><span data-stu-id="a7abb-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="a7abb-107">Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a7abb-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="a7abb-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a7abb-108">Example</span></span>

<span data-ttu-id="a7abb-109">Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="a7abb-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="a7abb-110">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="a7abb-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="a7abb-111">Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.</span><span class="sxs-lookup"><span data-stu-id="a7abb-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="a7abb-112">Элементы структуры защитить нельзя, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="a7abb-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="a7abb-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a7abb-113">Example</span></span>

<span data-ttu-id="a7abb-114">В этом примере класс `DerivedPoint` является производным от класса `Point`.</span><span class="sxs-lookup"><span data-stu-id="a7abb-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="a7abb-115">В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.</span><span class="sxs-lookup"><span data-stu-id="a7abb-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="a7abb-116">Если изменить уровни доступа `x` и `y` на [private](private.md), компилятор выдаст сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="a7abb-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="a7abb-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a7abb-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a7abb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a7abb-118">See also</span></span>

- [<span data-ttu-id="a7abb-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a7abb-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="a7abb-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a7abb-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a7abb-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a7abb-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a7abb-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="a7abb-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a7abb-123">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="a7abb-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a7abb-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="a7abb-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="a7abb-125">public</span><span class="sxs-lookup"><span data-stu-id="a7abb-125">public</span></span>](public.md)
- [<span data-ttu-id="a7abb-126">private</span><span class="sxs-lookup"><span data-stu-id="a7abb-126">private</span></span>](private.md)
- [<span data-ttu-id="a7abb-127">internal</span><span class="sxs-lookup"><span data-stu-id="a7abb-127">internal</span></span>](internal.md)
- <span data-ttu-id="a7abb-128">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a7abb-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>