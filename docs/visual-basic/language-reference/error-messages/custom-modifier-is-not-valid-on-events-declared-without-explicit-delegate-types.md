---
title: Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c1b57ccdaa9e04c837ecf7572bc164683a934b2d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273521"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="7a317-102">Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов</span><span class="sxs-lookup"><span data-stu-id="7a317-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="7a317-103">В отличие от событий ненастраиваемых `Custom Event` требует `As` предложение после имени события, которая явно задает тип делегата для события.</span><span class="sxs-lookup"><span data-stu-id="7a317-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="7a317-104">Обычные события могут быть определены с `As` предложение и явный тип делегата или списка параметров сразу после имени события.</span><span class="sxs-lookup"><span data-stu-id="7a317-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="7a317-105">**Идентификатор ошибки:** BC31122</span><span class="sxs-lookup"><span data-stu-id="7a317-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a317-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7a317-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7a317-107">Определите делегат с такой же список параметров, как пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="7a317-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="7a317-108">Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, а затем соответствующий делегат будет следующим.</span><span class="sxs-lookup"><span data-stu-id="7a317-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="7a317-109">Замените список параметров пользовательского события с `As` предложение, определяющее тип делегата.</span><span class="sxs-lookup"><span data-stu-id="7a317-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="7a317-110">В примере `Custom Event` объявление можно переписать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7a317-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7a317-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7a317-111">Example</span></span>  
 <span data-ttu-id="7a317-112">В этом примере объявляется `Custom Event` и указывает необходимые `As` предложение с типом делегата.</span><span class="sxs-lookup"><span data-stu-id="7a317-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7a317-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7a317-113">See also</span></span>
- [<span data-ttu-id="7a317-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="7a317-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="7a317-115">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="7a317-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="7a317-116">События</span><span class="sxs-lookup"><span data-stu-id="7a317-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
