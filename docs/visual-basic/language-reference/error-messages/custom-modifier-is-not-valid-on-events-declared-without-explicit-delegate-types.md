---
title: '&#39; Настраиваемый &#39; модификатор недопустим для событий, объявленных без явных делегируемых типов'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 844bd033ea05e373b04a04f80777af77179c1263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="bca5a-102">&#39; Настраиваемый &#39; модификатор недопустим для событий, объявленных без явных делегируемых типов</span><span class="sxs-lookup"><span data-stu-id="bca5a-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="bca5a-103">В отличие от событий от обычного `Custom Event` объявления требуется `As` предложение после имени события, которое явно указывает тип делегата для события.</span><span class="sxs-lookup"><span data-stu-id="bca5a-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="bca5a-104">Обычные события могут быть определены с `As` предложения и явного типа делегата или списка параметров сразу после имени события.</span><span class="sxs-lookup"><span data-stu-id="bca5a-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="bca5a-105">**Идентификатор ошибки:** BC31122</span><span class="sxs-lookup"><span data-stu-id="bca5a-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bca5a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bca5a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="bca5a-107">Определите делегат с тем же списком параметров, что пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="bca5a-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="bca5a-108">Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, то соответствующий делегат будет следующим.</span><span class="sxs-lookup"><span data-stu-id="bca5a-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="bca5a-109">Замените список параметров пользовательского события с `As` предложение указания типа делегата.</span><span class="sxs-lookup"><span data-stu-id="bca5a-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="bca5a-110">В примере `Custom Event` объявления можно переписать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bca5a-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="bca5a-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bca5a-111">Example</span></span>  
 <span data-ttu-id="bca5a-112">В этом примере объявляется `Custom Event` и указывает необходимые `As` предложения с типом делегата.</span><span class="sxs-lookup"><span data-stu-id="bca5a-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bca5a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bca5a-113">See Also</span></span>  
 [<span data-ttu-id="bca5a-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="bca5a-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="bca5a-115">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="bca5a-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="bca5a-116">События</span><span class="sxs-lookup"><span data-stu-id="bca5a-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
