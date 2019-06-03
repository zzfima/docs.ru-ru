---
title: Ключевое слово namespace. Справочник по C#
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: df921ecc670bf12411dc8b0d828d6c19bb0a1aec
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422744"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="a52e6-102">namespace (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a52e6-102">namespace (C# Reference)</span></span>

<span data-ttu-id="a52e6-103">Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="a52e6-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="a52e6-104">Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.</span><span class="sxs-lookup"><span data-stu-id="a52e6-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="a52e6-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="a52e6-105">Remarks</span></span>

<span data-ttu-id="a52e6-106">В пространстве имен можно объявить ноль или больше следующих типов:</span><span class="sxs-lookup"><span data-stu-id="a52e6-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="a52e6-107">другое пространство имен</span><span class="sxs-lookup"><span data-stu-id="a52e6-107">another namespace</span></span>

- [<span data-ttu-id="a52e6-108">class</span><span class="sxs-lookup"><span data-stu-id="a52e6-108">class</span></span>](class.md)

- [<span data-ttu-id="a52e6-109">interface</span><span class="sxs-lookup"><span data-stu-id="a52e6-109">interface</span></span>](interface.md)

- [<span data-ttu-id="a52e6-110">struct</span><span class="sxs-lookup"><span data-stu-id="a52e6-110">struct</span></span>](struct.md)

- [<span data-ttu-id="a52e6-111">enum</span><span class="sxs-lookup"><span data-stu-id="a52e6-111">enum</span></span>](enum.md)

- [<span data-ttu-id="a52e6-112">delegate</span><span class="sxs-lookup"><span data-stu-id="a52e6-112">delegate</span></span>](delegate.md)

<span data-ttu-id="a52e6-113">Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a52e6-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="a52e6-114">Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="a52e6-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="a52e6-115">Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a52e6-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="a52e6-116">Пространства имен неявно имеют общий доступ, и это невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="a52e6-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="a52e6-117">Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a52e6-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="a52e6-118">Пространство имен можно определить в двух или нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="a52e6-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="a52e6-119">Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="a52e6-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="a52e6-120">Пример</span><span class="sxs-lookup"><span data-stu-id="a52e6-120">Example</span></span>

<span data-ttu-id="a52e6-121">В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a52e6-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="a52e6-122">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="a52e6-122">Related resources</span></span>

<span data-ttu-id="a52e6-123">Дополнительные сведения об использовании пространств имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a52e6-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="a52e6-124">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="a52e6-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="a52e6-125">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="a52e6-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="a52e6-126">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="a52e6-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="a52e6-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a52e6-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a52e6-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a52e6-128">See also</span></span>

- [<span data-ttu-id="a52e6-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a52e6-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="a52e6-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a52e6-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a52e6-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a52e6-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a52e6-132">using</span><span class="sxs-lookup"><span data-stu-id="a52e6-132">using</span></span>](using-directive.md)
- [<span data-ttu-id="a52e6-133">using static</span><span class="sxs-lookup"><span data-stu-id="a52e6-133">using static</span></span>](using-static.md)
