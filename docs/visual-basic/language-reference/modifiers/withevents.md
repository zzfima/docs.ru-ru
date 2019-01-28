---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: e1a6cecdf724603b8f4617fe4e8b5ef2c0acdeff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624565"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="82c1f-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82c1f-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="82c1f-103">Указывает, что один или несколько объявленных переменных-членов ссылаются на экземпляр класса, который может порождать события.</span><span class="sxs-lookup"><span data-stu-id="82c1f-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82c1f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="82c1f-104">Remarks</span></span>  
 <span data-ttu-id="82c1f-105">Если переменная определена с помощью `WithEvents`, декларативно, можно указать, что метод обрабатывает события переменной с помощью `Handles` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="82c1f-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="82c1f-106">Можно использовать `WithEvents` только на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="82c1f-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="82c1f-107">Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модуля и не может быть исходный файл, пространство имен, структуры или процедуры.</span><span class="sxs-lookup"><span data-stu-id="82c1f-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="82c1f-108">Нельзя использовать `WithEvents` для членов структуры.</span><span class="sxs-lookup"><span data-stu-id="82c1f-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="82c1f-109">Можно объявить только отдельные переменные, не массивы — с `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="82c1f-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="82c1f-110">Правила</span><span class="sxs-lookup"><span data-stu-id="82c1f-110">Rules</span></span>  
  
-   <span data-ttu-id="82c1f-111">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="82c1f-111">**Element Types.**</span></span> <span data-ttu-id="82c1f-112">Необходимо объявить `WithEvents` переменные должны быть объектные переменные, чтобы они способны принять экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="82c1f-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="82c1f-113">Тем не менее, нельзя объявлять их как `Object`.</span><span class="sxs-lookup"><span data-stu-id="82c1f-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="82c1f-114">Их необходимо объявить как определенный класс, который может инициировать события.</span><span class="sxs-lookup"><span data-stu-id="82c1f-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="82c1f-115">`WithEvents` Модификатор может использоваться в этом контексте: [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="82c1f-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c1f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="82c1f-116">See also</span></span>
- [<span data-ttu-id="82c1f-117">Handles</span><span class="sxs-lookup"><span data-stu-id="82c1f-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="82c1f-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="82c1f-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="82c1f-119">События</span><span class="sxs-lookup"><span data-stu-id="82c1f-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
