---
title: "&quot;&lt;typename&gt;&quot; является типом делегата | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 55532e269a7d6756157d324a2db14320df5d3f55
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="bd38f-102">"&lt;typename&gt;" является типом делегата</span><span class="sxs-lookup"><span data-stu-id="bd38f-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="bd38f-103">"\<typename настроек" является типом делегата.</span><span class="sxs-lookup"><span data-stu-id="bd38f-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="bd38f-104">Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов.</span><span class="sxs-lookup"><span data-stu-id="bd38f-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="bd38f-105">Часто выражение AddressOf может использоваться вместо конструкции делегата.</span><span class="sxs-lookup"><span data-stu-id="bd38f-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="bd38f-106">A `New` создании экземпляра класса делегата передает недопустимый список аргументов в конструктор делегата.</span><span class="sxs-lookup"><span data-stu-id="bd38f-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="bd38f-107">Можно указать только один `AddressOf` выражение при создании нового экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="bd38f-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="bd38f-108">Эта ошибка может произойти, если не передать аргументы конструктора делегата, если передать несколько аргументов, или если передается один аргумент, не является допустимым `AddressOf` выражение.</span><span class="sxs-lookup"><span data-stu-id="bd38f-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="bd38f-109">**Идентификатор ошибки:** BC32008</span><span class="sxs-lookup"><span data-stu-id="bd38f-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd38f-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bd38f-110">To correct this error</span></span>  
  
-   <span data-ttu-id="bd38f-111">Использовать единую `AddressOf` выражение в списке аргументов для класса делегата в `New` предложения.</span><span class="sxs-lookup"><span data-stu-id="bd38f-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd38f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bd38f-112">See Also</span></span>  
 <span data-ttu-id="bd38f-113">[Оператор New](../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="bd38f-113">[New Operator](../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="bd38f-114"> [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="bd38f-114"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="bd38f-115"> [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd38f-115"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="bd38f-116"> [Практическое руководство. Вызов метода делегата](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="bd38f-116"> [How to: Invoke a Delegate Method](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
