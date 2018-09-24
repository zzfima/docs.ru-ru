---
title: Ключевое слово base (справочник по C#)
description: Сведения о ключевом слове base, которое используется для доступа к членам базового класса из производного класса в C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: 8719ab79273701173530760ad1bec837c4f4302d
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583071"
---
# <a name="base-c-reference"></a><span data-ttu-id="7ba60-103">base (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7ba60-103">base (C# Reference)</span></span>

<span data-ttu-id="7ba60-104">Ключевое слово `base` используется для доступа к членам базового из производного класса в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="7ba60-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="7ba60-105">Вызов метода базового класса, который был переопределен другим методом.</span><span class="sxs-lookup"><span data-stu-id="7ba60-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="7ba60-106">Определение конструктора базового класса, который должен вызываться при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="7ba60-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="7ba60-107">Доступ к базовому классу разрешен только в конструкторе, методе экземпляра или методе доступа к свойству экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7ba60-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="7ba60-108">Использование ключевого слова `base` в статическом методе является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="7ba60-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="7ba60-109">Доступ осуществляется к базовому классу, заданному в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="7ba60-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="7ba60-110">Например, если указать `class ClassB : ClassA`, члены ClassA будут доступны из ClassB независимо от базового класса ClassA.</span><span class="sxs-lookup"><span data-stu-id="7ba60-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="7ba60-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7ba60-111">Example</span></span>

<span data-ttu-id="7ba60-112">В приведенном ниже примере метод `Getinfo` присутствует как в базовом классе `Person`, так и в производном классе `Employee`.</span><span class="sxs-lookup"><span data-stu-id="7ba60-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="7ba60-113">С помощью ключевого слова `base` можно вызвать метод `Getinfo` базового класса из производного класса.</span><span class="sxs-lookup"><span data-stu-id="7ba60-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="7ba60-114">Дополнительные примеры см. в разделах [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) и [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="7ba60-114">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="7ba60-115">Пример</span><span class="sxs-lookup"><span data-stu-id="7ba60-115">Example</span></span>

<span data-ttu-id="7ba60-116">В этом примере показано, как задать конструктор базового класса, вызываемый при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="7ba60-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="7ba60-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7ba60-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7ba60-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7ba60-118">See also</span></span>

- [<span data-ttu-id="7ba60-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7ba60-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7ba60-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7ba60-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7ba60-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7ba60-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="7ba60-122">this</span><span class="sxs-lookup"><span data-stu-id="7ba60-122">this</span></span>](../../../csharp/language-reference/keywords/this.md)