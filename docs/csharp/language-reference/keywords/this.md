---
title: Справочник по C#. Ключевое слово this
description: Ключевое слово this (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715106"
---
# <a name="this-c-reference"></a><span data-ttu-id="c40e9-103">this (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c40e9-103">this (C# Reference)</span></span>

<span data-ttu-id="c40e9-104">Ключевое слово `this` ссылается на текущий экземпляр класса, а также используется в качестве модификатора первого параметра метода расширения.</span><span class="sxs-lookup"><span data-stu-id="c40e9-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="c40e9-105">В этой статье рассматривается использование `this` с экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="c40e9-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="c40e9-106">Дополнительные сведения об использовании этого ключевого слова в методах расширения см. в разделе [Методы расширения](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c40e9-106">For more information about its use in extension methods, see [Extension Methods](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="c40e9-107">Ниже перечислены наиболее частые способы использования `this`.</span><span class="sxs-lookup"><span data-stu-id="c40e9-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="c40e9-108">Для квалификации элементов, скрытых одинаковыми именами, например:</span><span class="sxs-lookup"><span data-stu-id="c40e9-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="c40e9-109">Для передачи другим методам объекта в качестве параметра, например:</span><span class="sxs-lookup"><span data-stu-id="c40e9-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="c40e9-110">Для объявления индексаторов, например:</span><span class="sxs-lookup"><span data-stu-id="c40e9-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="c40e9-111">У статических функций-членов нет указателя `this`, так как они существуют только на уровне класса и не являются частями объектов.</span><span class="sxs-lookup"><span data-stu-id="c40e9-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="c40e9-112">Использование `this` в статическом методе приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="c40e9-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="c40e9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c40e9-113">Example</span></span>

<span data-ttu-id="c40e9-114">В этом примере `this` используется для квалификации членов класса `Employee`, `name` и `alias`, которые скрыты одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="c40e9-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="c40e9-115">Это ключевое слово также используется для передачи объекта в метод `CalcTax`, который принадлежит другому классу.</span><span class="sxs-lookup"><span data-stu-id="c40e9-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="c40e9-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c40e9-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c40e9-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c40e9-117">See also</span></span>

- [<span data-ttu-id="c40e9-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c40e9-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c40e9-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c40e9-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c40e9-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="c40e9-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c40e9-121">base</span><span class="sxs-lookup"><span data-stu-id="c40e9-121">base</span></span>](base.md)
- [<span data-ttu-id="c40e9-122">Методы</span><span class="sxs-lookup"><span data-stu-id="c40e9-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
