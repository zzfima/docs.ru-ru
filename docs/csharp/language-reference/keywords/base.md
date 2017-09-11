---
title: "base (Справочник по C#)"
description: "Сведения о ключевом слове base, которое используется для доступа к членам базового класса из производного класса в C#."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
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
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: b3a389d92373b6ba5995a7644b0440f9d8fad9ac
ms.contentlocale: ru-ru
ms.lasthandoff: 08/17/2017

---
# <a name="base-c-reference"></a><span data-ttu-id="eaa53-103">base (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="eaa53-103">base (C# Reference)</span></span>

<span data-ttu-id="eaa53-104">Ключевое слово `base` используется для доступа к членам базового из производного класса в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="eaa53-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="eaa53-105">Вызов метода базового класса, который был переопределен другим методом.</span><span class="sxs-lookup"><span data-stu-id="eaa53-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="eaa53-106">Определение конструктора базового класса, который должен вызываться при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="eaa53-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="eaa53-107">Доступ к базовому классу разрешен только в конструкторе, методе экземпляра или методе доступа к свойству экземпляра.</span><span class="sxs-lookup"><span data-stu-id="eaa53-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="eaa53-108">Использование ключевого слова `base` в статическом методе является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="eaa53-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="eaa53-109">Доступ осуществляется к базовому классу, заданному в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="eaa53-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="eaa53-110">Например, если указать `class ClassB : ClassA`, члены ClassA будут доступны из ClassB независимо от базового класса ClassA.</span><span class="sxs-lookup"><span data-stu-id="eaa53-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="eaa53-111">Пример</span><span class="sxs-lookup"><span data-stu-id="eaa53-111">Example</span></span>
<span data-ttu-id="eaa53-112">В приведенном ниже примере метод `Getinfo` присутствует как в базовом классе `Person`, так и в производном классе `Employee`.</span><span class="sxs-lookup"><span data-stu-id="eaa53-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="eaa53-113">С помощью ключевого слова `base` можно вызвать метод `Getinfo` базового класса из производного класса.</span><span class="sxs-lookup"><span data-stu-id="eaa53-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

<span data-ttu-id="eaa53-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eaa53-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span></span>

<span data-ttu-id="eaa53-115">Дополнительные примеры см. в разделах [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) и [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="eaa53-115">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="eaa53-116">Пример</span><span class="sxs-lookup"><span data-stu-id="eaa53-116">Example</span></span>
<span data-ttu-id="eaa53-117">В этом примере показано, как задать конструктор базового класса, вызываемый при создании экземпляров производного класса.</span><span class="sxs-lookup"><span data-stu-id="eaa53-117">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

<span data-ttu-id="eaa53-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="eaa53-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="eaa53-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="eaa53-119">C# language specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="eaa53-120">См. также</span><span class="sxs-lookup"><span data-stu-id="eaa53-120">See also</span></span>
 <span data-ttu-id="eaa53-121">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="eaa53-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="eaa53-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eaa53-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="eaa53-123">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="eaa53-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="eaa53-124">this</span><span class="sxs-lookup"><span data-stu-id="eaa53-124">this</span></span>](../../../csharp/language-reference/keywords/this.md)
