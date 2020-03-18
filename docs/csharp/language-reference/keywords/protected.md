---
title: Справочник по C#. Ключевое слово protected
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: bec619d4f49bd26daa742c18c830909c14948adf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713187"
---
# <a name="protected-c-reference"></a><span data-ttu-id="d2b36-102">protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d2b36-102">protected (C# Reference)</span></span>

<span data-ttu-id="d2b36-103">Ключевое слово `protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="d2b36-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="d2b36-104">Эта страница содержит доступ `protected`.</span><span class="sxs-lookup"><span data-stu-id="d2b36-104">This page covers `protected` access.</span></span> <span data-ttu-id="d2b36-105">Ключевое слово `protected` также является частью модификаторов доступа [`protected internal`](protected-internal.md) и [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="d2b36-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="d2b36-106">Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.</span><span class="sxs-lookup"><span data-stu-id="d2b36-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="d2b36-107">Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d2b36-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="d2b36-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d2b36-108">Example</span></span>

<span data-ttu-id="d2b36-109">Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="d2b36-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="d2b36-110">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="d2b36-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="d2b36-111">Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.</span><span class="sxs-lookup"><span data-stu-id="d2b36-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="d2b36-112">Элементы структуры защитить нельзя, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="d2b36-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="d2b36-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d2b36-113">Example</span></span>

<span data-ttu-id="d2b36-114">В этом примере класс `DerivedPoint` является производным от класса `Point`.</span><span class="sxs-lookup"><span data-stu-id="d2b36-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="d2b36-115">В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.</span><span class="sxs-lookup"><span data-stu-id="d2b36-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="d2b36-116">Если изменить уровни доступа `x` и `y` на [private](private.md), компилятор выдаст сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="d2b36-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="d2b36-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d2b36-117">C# language specification</span></span>  

<span data-ttu-id="d2b36-118">Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="d2b36-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="d2b36-119">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="d2b36-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2b36-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2b36-120">See also</span></span>

- [<span data-ttu-id="d2b36-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d2b36-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d2b36-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d2b36-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d2b36-123">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d2b36-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d2b36-124">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="d2b36-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="d2b36-125">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="d2b36-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="d2b36-126">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="d2b36-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="d2b36-127">public</span><span class="sxs-lookup"><span data-stu-id="d2b36-127">public</span></span>](public.md)
- [<span data-ttu-id="d2b36-128">private</span><span class="sxs-lookup"><span data-stu-id="d2b36-128">private</span></span>](private.md)
- [<span data-ttu-id="d2b36-129">internal</span><span class="sxs-lookup"><span data-stu-id="d2b36-129">internal</span></span>](internal.md)
- <span data-ttu-id="d2b36-130">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d2b36-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
