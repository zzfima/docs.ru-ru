---
title: <typename> является типом делегата
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 45dc0403468fa40888a6c5e6bdfe6ca782e98325
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664165"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="770f8-102">"\<typename >" является типом делегата</span><span class="sxs-lookup"><span data-stu-id="770f8-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="770f8-103">"\<typename >" является типом делегата.</span><span class="sxs-lookup"><span data-stu-id="770f8-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="770f8-104">Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов.</span><span class="sxs-lookup"><span data-stu-id="770f8-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="770f8-105">Часто выражение AddressOf может использоваться вместо конструкции делегата.</span><span class="sxs-lookup"><span data-stu-id="770f8-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="770f8-106">Объект `New` создании экземпляра класса делегата передает список недопустимый аргумент конструктора делегата.</span><span class="sxs-lookup"><span data-stu-id="770f8-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="770f8-107">Можно указать только один `AddressOf` выражения при создании нового экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="770f8-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="770f8-108">Эта ошибка может возникнуть, если не передать аргументы конструктора делегата, если можно передать несколько аргументов, или если передать один аргумент, не является допустимым `AddressOf` выражение.</span><span class="sxs-lookup"><span data-stu-id="770f8-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="770f8-109">**Идентификатор ошибки:** BC32008</span><span class="sxs-lookup"><span data-stu-id="770f8-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="770f8-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="770f8-110">To correct this error</span></span>  
  
- <span data-ttu-id="770f8-111">Использовать единую `AddressOf` выражение в списке аргументов для класса делегата в `New` предложение.</span><span class="sxs-lookup"><span data-stu-id="770f8-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="770f8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="770f8-112">See also</span></span>

- [<span data-ttu-id="770f8-113">Оператор New</span><span class="sxs-lookup"><span data-stu-id="770f8-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="770f8-114">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="770f8-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="770f8-115">Делегаты</span><span class="sxs-lookup"><span data-stu-id="770f8-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="770f8-116">Практическое руководство. Вызов метода делегата</span><span class="sxs-lookup"><span data-stu-id="770f8-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
