---
title: Справочник по C#. Ключевое слово base
description: Сведения о ключевом слове base, которое используется для доступа к членам базового класса из производного класса в C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: a4686fc5d4245a50de5d77dc0e71c231772f40ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713772"
---
# <a name="base-c-reference"></a><span data-ttu-id="af25f-103">base (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="af25f-103">base (C# Reference)</span></span>

<span data-ttu-id="af25f-104">Ключевое слово `base` используется для доступа к членам базового из производного класса в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="af25f-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="af25f-105">Вызов метода базового класса, который был переопределен другим методом.</span><span class="sxs-lookup"><span data-stu-id="af25f-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="af25f-106">Определение конструктора базового класса, который должен вызываться при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="af25f-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="af25f-107">Доступ к базовому классу разрешен только в конструкторе, методе экземпляра или методе доступа к свойству экземпляра.</span><span class="sxs-lookup"><span data-stu-id="af25f-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="af25f-108">Использование ключевого слова `base` в статическом методе является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="af25f-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="af25f-109">Доступ осуществляется к базовому классу, заданному в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="af25f-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="af25f-110">Например, если указать `class ClassB : ClassA`, члены ClassA будут доступны из ClassB независимо от базового класса ClassA.</span><span class="sxs-lookup"><span data-stu-id="af25f-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="af25f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="af25f-111">Example</span></span>

<span data-ttu-id="af25f-112">В приведенном ниже примере метод `Person` присутствует как в базовом классе `Employee`, так и в производном классе `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="af25f-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="af25f-113">С помощью ключевого слова `base` можно вызвать метод `Getinfo` базового класса из производного класса.</span><span class="sxs-lookup"><span data-stu-id="af25f-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="af25f-114">Дополнительные примеры см. в разделах [new](new-modifier.md), [virtual](virtual.md) и [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="af25f-114">For additional examples, see [new](new-modifier.md), [virtual](virtual.md), and [override](override.md).</span></span>

## <a name="example"></a><span data-ttu-id="af25f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="af25f-115">Example</span></span>

<span data-ttu-id="af25f-116">В этом примере показано, как задать конструктор базового класса, вызываемый при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="af25f-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="af25f-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="af25f-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="af25f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af25f-118">See also</span></span>

- [<span data-ttu-id="af25f-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="af25f-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="af25f-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="af25f-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="af25f-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="af25f-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="af25f-122">this</span><span class="sxs-lookup"><span data-stu-id="af25f-122">this</span></span>](./this.md)
