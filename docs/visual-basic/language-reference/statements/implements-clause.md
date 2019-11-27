---
title: Предложение Implements
ms.date: 07/20/2015
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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345876"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="68eed-102">Предложение Implements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68eed-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="68eed-103">Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="68eed-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68eed-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="68eed-104">Remarks</span></span>  
<span data-ttu-id="68eed-105">Ключевое слово `Implements` не совпадает с [оператором Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="68eed-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="68eed-106">Используйте оператор `Implements`, чтобы указать, что класс или структура реализует один или несколько интерфейсов, а затем для каждого элемента вы используете `Implements` ключевое слово, чтобы указать, какой интерфейс и какой член он реализует.</span><span class="sxs-lookup"><span data-stu-id="68eed-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="68eed-107">Если класс или структура реализует интерфейс, он должен включать инструкцию `Implements` сразу после оператора [Class](../../../visual-basic/language-reference/statements/class-statement.md) или [Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и она должна реализовывать все члены, определенные интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="68eed-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="68eed-108">Воссоздании</span><span class="sxs-lookup"><span data-stu-id="68eed-108">Reimplementation</span></span>  
<span data-ttu-id="68eed-109">В производном классе можно повторно реализовать член интерфейса, который уже реализован в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="68eed-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="68eed-110">Это отличается от переопределения члена базового класса в следующих отношениях.</span><span class="sxs-lookup"><span data-stu-id="68eed-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="68eed-111">Член базового класса не обязательно должен быть [переопределяемым](../../../visual-basic/language-reference/modifiers/overridable.md) для повторной реализации.</span><span class="sxs-lookup"><span data-stu-id="68eed-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="68eed-112">Элемент можно повторно реализовать с другим именем.</span><span class="sxs-lookup"><span data-stu-id="68eed-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="68eed-113">Ключевое слово `Implements` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="68eed-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="68eed-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="68eed-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="68eed-115">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="68eed-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="68eed-116">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="68eed-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="68eed-117">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="68eed-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="68eed-118">См. также</span><span class="sxs-lookup"><span data-stu-id="68eed-118">See also</span></span>

- [<span data-ttu-id="68eed-119">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="68eed-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="68eed-120">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="68eed-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="68eed-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="68eed-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="68eed-122">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="68eed-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
