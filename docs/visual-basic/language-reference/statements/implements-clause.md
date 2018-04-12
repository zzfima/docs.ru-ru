---
title: Предложение Implements (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73f66eda29e37fda15b4c838da5a0458684131da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="05f44-102">Предложение Implements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05f44-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="05f44-103">Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="05f44-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05f44-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="05f44-104">Remarks</span></span>  
<span data-ttu-id="05f44-105">`Implements` Ключевое слово не совпадает с [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="05f44-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="05f44-106">Вы используете `Implements` инструкцию, чтобы указать, что класс или структура реализует один или несколько интерфейсов, и затем для каждого элемента используется `Implements` ключевое слово, чтобы указать, какой интерфейс и какой элемент, он реализует.</span><span class="sxs-lookup"><span data-stu-id="05f44-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="05f44-107">Если класс или структура реализует интерфейс, она должна включать `Implements` инструкции сразу после [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) или [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и он должен реализовывать все члены определяется интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="05f44-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="05f44-108">Повторная реализация</span><span class="sxs-lookup"><span data-stu-id="05f44-108">Reimplementation</span></span>  
<span data-ttu-id="05f44-109">Производный класс может повторно реализовать член интерфейса, который уже реализован базовым классом.</span><span class="sxs-lookup"><span data-stu-id="05f44-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="05f44-110">Это отличается от переопределения члена базового класса в следующих аспектах:</span><span class="sxs-lookup"><span data-stu-id="05f44-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="05f44-111">Член базового класса не требуется быть [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) для быть воссозданы.</span><span class="sxs-lookup"><span data-stu-id="05f44-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="05f44-112">Можно реализовать элемент под другим именем.</span><span class="sxs-lookup"><span data-stu-id="05f44-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="05f44-113">`Implements` Ключевое слово может использоваться в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="05f44-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="05f44-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="05f44-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="05f44-115">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="05f44-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="05f44-116">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="05f44-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="05f44-117">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="05f44-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="05f44-118">См. также</span><span class="sxs-lookup"><span data-stu-id="05f44-118">See Also</span></span>  
 [<span data-ttu-id="05f44-119">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="05f44-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="05f44-120">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="05f44-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="05f44-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="05f44-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="05f44-122">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="05f44-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
