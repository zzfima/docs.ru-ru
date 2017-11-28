---
title: "namespace (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76cc1adc21f6cfadc93da58250336705e43e333a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-c-reference"></a><span data-ttu-id="d2e5b-102">namespace (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d2e5b-102">namespace (C# Reference)</span></span>
<span data-ttu-id="d2e5b-103">Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="d2e5b-104">Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="d2e5b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2e5b-105">Remarks</span></span>  
 <span data-ttu-id="d2e5b-106">В пространстве имен можно объявить один или несколько следующих типов:</span><span class="sxs-lookup"><span data-stu-id="d2e5b-106">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="d2e5b-107">другое пространство имен</span><span class="sxs-lookup"><span data-stu-id="d2e5b-107">another namespace</span></span>  
  
-   [<span data-ttu-id="d2e5b-108">class</span><span class="sxs-lookup"><span data-stu-id="d2e5b-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="d2e5b-109">interface</span><span class="sxs-lookup"><span data-stu-id="d2e5b-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="d2e5b-110">struct</span><span class="sxs-lookup"><span data-stu-id="d2e5b-110">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="d2e5b-111">enum</span><span class="sxs-lookup"><span data-stu-id="d2e5b-111">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="d2e5b-112">delegate</span><span class="sxs-lookup"><span data-stu-id="d2e5b-112">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="d2e5b-113">Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="d2e5b-114">Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="d2e5b-115">Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="d2e5b-116">Пространства имен неявно имеют общий доступ, и это невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="d2e5b-117">Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d2e5b-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="d2e5b-118">Пространство имен можно определить в двух или нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="d2e5b-119">Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="d2e5b-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="d2e5b-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d2e5b-120">Example</span></span>  
 <span data-ttu-id="d2e5b-121">В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d2e5b-121">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a><span data-ttu-id="d2e5b-122">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d2e5b-122">For More Information</span></span>  
 <span data-ttu-id="d2e5b-123">Дополнительные сведения об использовании пространств имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d2e5b-123">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="d2e5b-124">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="d2e5b-124">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="d2e5b-125">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="d2e5b-125">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="d2e5b-126">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="d2e5b-126">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="d2e5b-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d2e5b-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2e5b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d2e5b-128">See Also</span></span>  
 [<span data-ttu-id="d2e5b-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d2e5b-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d2e5b-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d2e5b-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d2e5b-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d2e5b-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d2e5b-132">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="d2e5b-132">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="d2e5b-133">using</span><span class="sxs-lookup"><span data-stu-id="d2e5b-133">using</span></span>](../../../csharp/language-reference/keywords/using.md)
