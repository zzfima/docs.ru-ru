---
title: Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 169cb49cc5abc76b7c52785392d0083b81a99450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803887"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="424a5-102">Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов</span><span class="sxs-lookup"><span data-stu-id="424a5-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="424a5-103">В отличие от событий ненастраиваемых `Custom Event` требует `As` предложение после имени события, которая явно задает тип делегата для события.</span><span class="sxs-lookup"><span data-stu-id="424a5-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="424a5-104">Обычные события могут быть определены с `As` предложение и явный тип делегата или списка параметров сразу после имени события.</span><span class="sxs-lookup"><span data-stu-id="424a5-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="424a5-105">**Идентификатор ошибки:** BC31122</span><span class="sxs-lookup"><span data-stu-id="424a5-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="424a5-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="424a5-106">To correct this error</span></span>  
  
1. <span data-ttu-id="424a5-107">Определите делегат с такой же список параметров, как пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="424a5-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="424a5-108">Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, а затем соответствующий делегат будет следующим.</span><span class="sxs-lookup"><span data-stu-id="424a5-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="424a5-109">Замените список параметров пользовательского события с `As` предложение, определяющее тип делегата.</span><span class="sxs-lookup"><span data-stu-id="424a5-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="424a5-110">В примере `Custom Event` объявление можно переписать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="424a5-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="424a5-111">Пример</span><span class="sxs-lookup"><span data-stu-id="424a5-111">Example</span></span>  
 <span data-ttu-id="424a5-112">В этом примере объявляется `Custom Event` и указывает необходимые `As` предложение с типом делегата.</span><span class="sxs-lookup"><span data-stu-id="424a5-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="424a5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="424a5-113">See also</span></span>

- [<span data-ttu-id="424a5-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="424a5-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="424a5-115">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="424a5-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="424a5-116">События</span><span class="sxs-lookup"><span data-stu-id="424a5-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
