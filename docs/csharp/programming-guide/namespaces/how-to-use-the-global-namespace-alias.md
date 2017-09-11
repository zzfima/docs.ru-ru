---
title: "Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
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
ms.openlocfilehash: 1252fc107d46b1d3a1cbef0a61708edc57253910
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="2f25e-102">Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2f25e-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="2f25e-103">Возможность доступа к члену в глобальном [пространстве имен](../../../csharp/language-reference/keywords/namespace.md) полезна в тех случаях, когда член может быть скрыт другой сущностью с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="2f25e-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="2f25e-104">Например, в следующем коде `Console` разрешается в `TestApp.Console` вместо типа `Console` в пространстве имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="2f25e-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 <span data-ttu-id="2f25e-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f25e-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span></span>  
  
 <span data-ttu-id="2f25e-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f25e-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span></span>  
  
 <span data-ttu-id="2f25e-107">При использовании `System.Console` по-прежнему возникает ошибка, поскольку пространство имен `System` скрыто классом `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="2f25e-107">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 <span data-ttu-id="2f25e-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f25e-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span></span>  
  
 <span data-ttu-id="2f25e-109">Тем не менее эту ошибку можно обойти с помощью `global::System.Console`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2f25e-109">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 <span data-ttu-id="2f25e-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f25e-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span></span>  
  
 <span data-ttu-id="2f25e-111">Если левый идентификатор равен `global`, поиск правого идентификатора начинается с глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2f25e-111">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="2f25e-112">Например, следующее объявление ссылается на `TestApp` как на член глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2f25e-112">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 <span data-ttu-id="2f25e-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f25e-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span></span>  
  
 <span data-ttu-id="2f25e-114">Очевидно, создавать собственные пространства имен с названием `System` не рекомендуется, и вряд ли вам когда-нибудь попадется код, где это сделано.</span><span class="sxs-lookup"><span data-stu-id="2f25e-114">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="2f25e-115">Тем не менее в крупных проектах существует вполне реальная вероятность того, что названия пространств имен будут в той или иной форме дублироваться.</span><span class="sxs-lookup"><span data-stu-id="2f25e-115">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="2f25e-116">В таких ситуациях вы можете гарантировать использование корневого пространства имен, указав квалификатор пространства имен global.</span><span class="sxs-lookup"><span data-stu-id="2f25e-116">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f25e-117">Пример</span><span class="sxs-lookup"><span data-stu-id="2f25e-117">Example</span></span>  
 <span data-ttu-id="2f25e-118">В этом примере пространство имен `System` используется для включения класса `TestClass`. Таким образом, следует использовать `global::System.Console` для ссылки на класс `System.Console`, который скрыт пространством имен `System`.</span><span class="sxs-lookup"><span data-stu-id="2f25e-118">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="2f25e-119">Также используется псевдоним `colAlias` для ссылки на пространство имен `System.Collections`. Таким образом, экземпляр <xref:System.Collections.Hashtable?displayProperty=fullName> был создан с использованием этого псевдонима вместо пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2f25e-119">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=fullName> was created using this alias instead of the namespace.</span></span>  
  
 <span data-ttu-id="2f25e-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f25e-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span></span>  
  
 <span data-ttu-id="2f25e-121">**A 1**</span><span class="sxs-lookup"><span data-stu-id="2f25e-121">**A 1**</span></span>  
<span data-ttu-id="2f25e-122">**B 2**</span><span class="sxs-lookup"><span data-stu-id="2f25e-122">**B 2**</span></span>  
<span data-ttu-id="2f25e-123">**C 3**</span><span class="sxs-lookup"><span data-stu-id="2f25e-123">**C 3**</span></span>   
## <a name="see-also"></a><span data-ttu-id="2f25e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2f25e-124">See Also</span></span>  
 <span data-ttu-id="2f25e-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f25e-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2f25e-126">[Пространства имен](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f25e-126">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="2f25e-127">[. Оператор](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2f25e-127">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="2f25e-128">[Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="2f25e-128">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="2f25e-129">extern</span><span class="sxs-lookup"><span data-stu-id="2f25e-129">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

