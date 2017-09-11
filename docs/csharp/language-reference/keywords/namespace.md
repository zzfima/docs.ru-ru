---
title: "namespace (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="namespace-c-reference"></a><span data-ttu-id="51f59-102">namespace (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="51f59-102">namespace (C# Reference)</span></span>
<span data-ttu-id="51f59-103">Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="51f59-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="51f59-104">Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.</span><span class="sxs-lookup"><span data-stu-id="51f59-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 <span data-ttu-id="51f59-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="51f59-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51f59-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="51f59-106">Remarks</span></span>  
 <span data-ttu-id="51f59-107">В пространстве имен можно объявить один или несколько следующих типов:</span><span class="sxs-lookup"><span data-stu-id="51f59-107">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="51f59-108">другое пространство имен</span><span class="sxs-lookup"><span data-stu-id="51f59-108">another namespace</span></span>  
  
-   [<span data-ttu-id="51f59-109">class</span><span class="sxs-lookup"><span data-stu-id="51f59-109">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="51f59-110">interface</span><span class="sxs-lookup"><span data-stu-id="51f59-110">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="51f59-111">struct</span><span class="sxs-lookup"><span data-stu-id="51f59-111">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="51f59-112">enum</span><span class="sxs-lookup"><span data-stu-id="51f59-112">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="51f59-113">delegate</span><span class="sxs-lookup"><span data-stu-id="51f59-113">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="51f59-114">Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51f59-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="51f59-115">Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="51f59-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="51f59-116">Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="51f59-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="51f59-117">Пространства имен неявно имеют общий доступ, и это невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="51f59-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="51f59-118">Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="51f59-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="51f59-119">Пространство имен можно определить в двух или нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="51f59-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="51f59-120">Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="51f59-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 <span data-ttu-id="51f59-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="51f59-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="51f59-122">Пример</span><span class="sxs-lookup"><span data-stu-id="51f59-122">Example</span></span>  
 <span data-ttu-id="51f59-123">В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51f59-123">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 <span data-ttu-id="51f59-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="51f59-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="51f59-125">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="51f59-125">For More Information</span></span>  
 <span data-ttu-id="51f59-126">Дополнительные сведения об использовании пространств имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="51f59-126">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="51f59-127">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="51f59-127">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="51f59-128">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="51f59-128">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="51f59-129">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="51f59-129">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="51f59-130">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="51f59-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51f59-131">См. также</span><span class="sxs-lookup"><span data-stu-id="51f59-131">See Also</span></span>  
 <span data-ttu-id="51f59-132">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="51f59-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="51f59-133">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="51f59-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="51f59-134">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="51f59-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="51f59-135">[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="51f59-135">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 [<span data-ttu-id="51f59-136">using</span><span class="sxs-lookup"><span data-stu-id="51f59-136">using</span></span>](../../../csharp/language-reference/keywords/using.md)

