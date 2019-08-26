---
title: Справочник по C#. Ключевое слово base
ms.custom: seodec18
description: Сведения о ключевом слове base, которое используется для доступа к членам базового класса из производного класса в C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: b882a8d1e5979ac184d184be379dd76f7bf3600f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602257"
---
# <a name="base-c-reference"></a><span data-ttu-id="55bec-103">base (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="55bec-103">base (C# Reference)</span></span>

<span data-ttu-id="55bec-104">Ключевое слово `base` используется для доступа к членам базового из производного класса в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="55bec-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="55bec-105">Вызов метода базового класса, который был переопределен другим методом.</span><span class="sxs-lookup"><span data-stu-id="55bec-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="55bec-106">Определение конструктора базового класса, который должен вызываться при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="55bec-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="55bec-107">Доступ к базовому классу разрешен только в конструкторе, методе экземпляра или методе доступа к свойству экземпляра.</span><span class="sxs-lookup"><span data-stu-id="55bec-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="55bec-108">Использование ключевого слова `base` в статическом методе является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="55bec-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="55bec-109">Доступ осуществляется к базовому классу, заданному в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="55bec-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="55bec-110">Например, если указать `class ClassB : ClassA`, члены ClassA будут доступны из ClassB независимо от базового класса ClassA.</span><span class="sxs-lookup"><span data-stu-id="55bec-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="55bec-111">Пример</span><span class="sxs-lookup"><span data-stu-id="55bec-111">Example</span></span>

<span data-ttu-id="55bec-112">В приведенном ниже примере метод `Getinfo` присутствует как в базовом классе `Person`, так и в производном классе `Employee`.</span><span class="sxs-lookup"><span data-stu-id="55bec-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="55bec-113">С помощью ключевого слова `base` можно вызвать метод `Getinfo` базового класса из производного класса.</span><span class="sxs-lookup"><span data-stu-id="55bec-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="55bec-114">Дополнительные примеры см. в разделах [new](new-modifier.md), [virtual](virtual.md) и [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="55bec-114">For additional examples, see [new](new-modifier.md), [virtual](virtual.md), and [override](override.md).</span></span>

## <a name="example"></a><span data-ttu-id="55bec-115">Пример</span><span class="sxs-lookup"><span data-stu-id="55bec-115">Example</span></span>

<span data-ttu-id="55bec-116">В этом примере показано, как задать конструктор базового класса, вызываемый при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="55bec-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="55bec-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="55bec-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="55bec-118">См. также</span><span class="sxs-lookup"><span data-stu-id="55bec-118">See also</span></span>

- [<span data-ttu-id="55bec-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="55bec-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="55bec-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="55bec-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="55bec-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="55bec-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="55bec-122">this</span><span class="sxs-lookup"><span data-stu-id="55bec-122">this</span></span>](./this.md)
