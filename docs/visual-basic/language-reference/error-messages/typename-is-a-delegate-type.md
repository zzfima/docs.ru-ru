---
title: '&#39;&lt;TypeName&gt; &#39; является типом делегата'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595652"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="1e9d6-102">&#39;&lt;TypeName&gt; &#39; является типом делегата</span><span class="sxs-lookup"><span data-stu-id="1e9d6-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="1e9d6-103">"\<typename >" является типом делегата.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="1e9d6-104">Конструкция делегата позволяет использовать только одно выражение AddressOf как список аргументов.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="1e9d6-105">Часто выражение AddressOf может использоваться вместо конструкции делегата.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="1e9d6-106">Объект `New` создании экземпляра класса делегата передает недопустимый список аргументов для конструктора делегата.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="1e9d6-107">Можно задать только одно `AddressOf` выражения при создании нового экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="1e9d6-108">Эта ошибка может возникнуть, если не передать аргументы конструктора делегата, если передать несколько аргументов, или если передается один аргумент, не является допустимым `AddressOf` выражение.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="1e9d6-109">**Идентификатор ошибки:** BC32008</span><span class="sxs-lookup"><span data-stu-id="1e9d6-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1e9d6-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1e9d6-110">To correct this error</span></span>  
  
-   <span data-ttu-id="1e9d6-111">Использовать отдельный `AddressOf` выражение в списке аргументов для класса делегата в `New` предложения.</span><span class="sxs-lookup"><span data-stu-id="1e9d6-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9d6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1e9d6-112">See Also</span></span>  
 [<span data-ttu-id="1e9d6-113">Оператор New</span><span class="sxs-lookup"><span data-stu-id="1e9d6-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="1e9d6-114">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="1e9d6-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="1e9d6-115">Делегаты</span><span class="sxs-lookup"><span data-stu-id="1e9d6-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="1e9d6-116">Практическое руководство. Вызов метода делегата</span><span class="sxs-lookup"><span data-stu-id="1e9d6-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
