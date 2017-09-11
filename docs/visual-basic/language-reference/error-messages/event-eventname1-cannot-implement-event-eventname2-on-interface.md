---
title: "Событие &quot;&lt;eventname1&gt;«не может реализовывать событие»&lt;eventname2&gt;«для интерфейса»&lt;интерфейс&gt;&quot; так как их делегируемые типы&lt;delegate1&gt;«и»&lt;delegate2&gt;&quot;не соответствуют | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
dev_langs:
- VB
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
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
ms.openlocfilehash: 340547d3673b651e988a6c1167bf7043360b04e4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="c2606-102">Событие "&lt;eventname1&gt;«не может реализовывать событие»&lt;eventname2&gt;«для интерфейса»&lt;интерфейс&gt;' так как их делегируемые типы&lt;delegate1&gt;«и»&lt;delegate2&gt;" не совпадают</span><span class="sxs-lookup"><span data-stu-id="c2606-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c2606-103">не может реализовать событие, поскольку тип делегата события не соответствует типу делегата события интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c2606-103"> cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="c2606-104">Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события.</span><span class="sxs-lookup"><span data-stu-id="c2606-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="c2606-105">Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="c2606-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="c2606-106">**Идентификатор ошибки:** BC31423</span><span class="sxs-lookup"><span data-stu-id="c2606-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2606-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c2606-107">To correct this error</span></span>  
  
-   <span data-ttu-id="c2606-108">Реализуйте события по отдельности.</span><span class="sxs-lookup"><span data-stu-id="c2606-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="c2606-109">—или—</span><span class="sxs-lookup"><span data-stu-id="c2606-109">—or—</span></span>  
  
-   <span data-ttu-id="c2606-110">Определите события в интерфейсе, используя `As` синтаксис и укажите тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="c2606-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2606-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c2606-111">See Also</span></span>  
 <span data-ttu-id="c2606-112">[Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c2606-112">[Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="c2606-113"> [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c2606-113"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="c2606-114"> [События](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="c2606-114"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
