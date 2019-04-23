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
ms.openlocfilehash: 4859c361b3321c1144204f63896152694f6ac5c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148763"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="05901-102">namespace (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="05901-102">namespace (C# Reference)</span></span>

<span data-ttu-id="05901-103">Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="05901-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="05901-104">Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.</span><span class="sxs-lookup"><span data-stu-id="05901-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="05901-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="05901-105">Remarks</span></span>

<span data-ttu-id="05901-106">В пространстве имен можно объявить ноль или больше следующих типов:</span><span class="sxs-lookup"><span data-stu-id="05901-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="05901-107">другое пространство имен</span><span class="sxs-lookup"><span data-stu-id="05901-107">another namespace</span></span>

- [<span data-ttu-id="05901-108">class</span><span class="sxs-lookup"><span data-stu-id="05901-108">class</span></span>](class.md)

- [<span data-ttu-id="05901-109">interface</span><span class="sxs-lookup"><span data-stu-id="05901-109">interface</span></span>](interface.md)

- [<span data-ttu-id="05901-110">struct</span><span class="sxs-lookup"><span data-stu-id="05901-110">struct</span></span>](struct.md)

- [<span data-ttu-id="05901-111">enum</span><span class="sxs-lookup"><span data-stu-id="05901-111">enum</span></span>](enum.md)

- [<span data-ttu-id="05901-112">delegate</span><span class="sxs-lookup"><span data-stu-id="05901-112">delegate</span></span>](delegate.md)

<span data-ttu-id="05901-113">Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05901-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="05901-114">Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="05901-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="05901-115">Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="05901-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="05901-116">Пространства имен неявно имеют общий доступ, и это невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="05901-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="05901-117">Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="05901-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="05901-118">Пространство имен можно определить в двух или нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="05901-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="05901-119">Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="05901-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="05901-120">Пример</span><span class="sxs-lookup"><span data-stu-id="05901-120">Example</span></span>

<span data-ttu-id="05901-121">В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="05901-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="05901-122">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="05901-122">Related resources</span></span>

<span data-ttu-id="05901-123">Дополнительные сведения об использовании пространств имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="05901-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="05901-124">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="05901-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="05901-125">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="05901-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="05901-126">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="05901-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="05901-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="05901-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="05901-128">См. также</span><span class="sxs-lookup"><span data-stu-id="05901-128">See also</span></span>

- [<span data-ttu-id="05901-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="05901-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="05901-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="05901-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="05901-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="05901-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="05901-132">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="05901-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="05901-133">using</span><span class="sxs-lookup"><span data-stu-id="05901-133">using</span></span>](using-directive.md)
- [<span data-ttu-id="05901-134">using static</span><span class="sxs-lookup"><span data-stu-id="05901-134">using static</span></span>](using-static.md)