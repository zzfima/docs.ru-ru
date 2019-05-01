---
title: <typename> является типом делегата
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c308805f5e73d740ff18a40d95b9cc2576ac95fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013599"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="72c9d-102">"\<typename >" является типом делегата</span><span class="sxs-lookup"><span data-stu-id="72c9d-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="72c9d-103">"\<typename >" является типом делегата.</span><span class="sxs-lookup"><span data-stu-id="72c9d-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="72c9d-104">Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов.</span><span class="sxs-lookup"><span data-stu-id="72c9d-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="72c9d-105">Часто выражение AddressOf может использоваться вместо конструкции делегата.</span><span class="sxs-lookup"><span data-stu-id="72c9d-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="72c9d-106">Объект `New` создании экземпляра класса делегата передает список недопустимый аргумент конструктора делегата.</span><span class="sxs-lookup"><span data-stu-id="72c9d-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="72c9d-107">Можно указать только один `AddressOf` выражения при создании нового экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="72c9d-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="72c9d-108">Эта ошибка может возникнуть, если не передать аргументы конструктора делегата, если можно передать несколько аргументов, или если передать один аргумент, не является допустимым `AddressOf` выражение.</span><span class="sxs-lookup"><span data-stu-id="72c9d-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="72c9d-109">**Идентификатор ошибки:** BC32008</span><span class="sxs-lookup"><span data-stu-id="72c9d-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72c9d-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="72c9d-110">To correct this error</span></span>  
  
- <span data-ttu-id="72c9d-111">Использовать единую `AddressOf` выражение в списке аргументов для класса делегата в `New` предложение.</span><span class="sxs-lookup"><span data-stu-id="72c9d-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c9d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="72c9d-112">See also</span></span>

- [<span data-ttu-id="72c9d-113">Оператор New</span><span class="sxs-lookup"><span data-stu-id="72c9d-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="72c9d-114">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="72c9d-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="72c9d-115">Делегаты</span><span class="sxs-lookup"><span data-stu-id="72c9d-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="72c9d-116">Практическое руководство. Вызов метода делегата</span><span class="sxs-lookup"><span data-stu-id="72c9d-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
