---
title: "Модификатор «Custom» недопустим для событий, объявленных без явных делегируемых типов | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
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
ms.openlocfilehash: 449e5a690f06ce35d1ccc799daf5f2c1ad1c6dac
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="eb047-102">Модификатор «Custom» недопустим для событий, объявленных без явных делегируемых типов</span><span class="sxs-lookup"><span data-stu-id="eb047-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="eb047-103">В отличие от событий от обычного `Custom Event` требует `As` предложение после имени события, которое явно указывает тип делегата для события.</span><span class="sxs-lookup"><span data-stu-id="eb047-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="eb047-104">Обычные события могут быть определены с `As` предложения и явного типа делегата или списка параметров сразу после имени события.</span><span class="sxs-lookup"><span data-stu-id="eb047-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="eb047-105">**Идентификатор ошибки:** BC31122</span><span class="sxs-lookup"><span data-stu-id="eb047-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb047-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="eb047-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="eb047-107">Определите делегат с такой же список параметров, как пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="eb047-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="eb047-108">Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, а затем соответствующий делегат будет следующим.</span><span class="sxs-lookup"><span data-stu-id="eb047-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     <span data-ttu-id="eb047-109">[!code-vb[VbVbalrEventError&18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb047-109">[!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span></span>  
  
2.  <span data-ttu-id="eb047-110">Замените список параметров пользовательского события с `As` предложения задающего тип делегата.</span><span class="sxs-lookup"><span data-stu-id="eb047-110">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="eb047-111">В примере `Custom Event` объявления можно переписать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="eb047-111">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     <span data-ttu-id="eb047-112">[!code-vb[VbVbalrEventError&19;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb047-112">[!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb047-113">Пример</span><span class="sxs-lookup"><span data-stu-id="eb047-113">Example</span></span>  
 <span data-ttu-id="eb047-114">В этом примере объявляется `Custom Event` и указывает необходимые `As` предложение с типом делегата.</span><span class="sxs-lookup"><span data-stu-id="eb047-114">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 <span data-ttu-id="eb047-115">[!code-vb[VbVbalrEventError&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb047-115">[!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb047-116">См. также</span><span class="sxs-lookup"><span data-stu-id="eb047-116">See Also</span></span>  
 <span data-ttu-id="eb047-117">[Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="eb047-117">[Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="eb047-118"> [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="eb047-118"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="eb047-119"> [События](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb047-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
