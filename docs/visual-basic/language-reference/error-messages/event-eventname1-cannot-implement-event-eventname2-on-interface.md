---
title: Событие &#39; &lt;имя_события1&gt; &#39; не может реализовывать событие &#39; &lt;имя_события2&gt; &#39; в интерфейсе &#39; &lt;интерфейс&gt; &#39; из-за их делегируемые типы &#39; &lt;delegate1&gt; &#39; и &#39; &lt;delegate2&gt; &#39; не совпадают
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 41f5984458eb17db04f20b292a0d80783093dcb4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="4c687-102">Событие &#39; &lt;имя_события1&gt; &#39; не может реализовывать событие &#39; &lt;имя_события2&gt; &#39; в интерфейсе &#39; &lt;интерфейс&gt; &#39; из-за их делегируемые типы &#39; &lt;delegate1&gt; &#39; и &#39; &lt;delegate2&gt; &#39; не совпадают</span><span class="sxs-lookup"><span data-stu-id="4c687-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
<span data-ttu-id="4c687-103">Visual Basic не может реализовать событие, поскольку тип делегата события не соответствует типу делегата события интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4c687-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="4c687-104">Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события.</span><span class="sxs-lookup"><span data-stu-id="4c687-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="4c687-105">Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="4c687-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="4c687-106">**Идентификатор ошибки:** BC31423</span><span class="sxs-lookup"><span data-stu-id="4c687-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c687-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4c687-107">To correct this error</span></span>  
  
-   <span data-ttu-id="4c687-108">Реализуйте события по отдельности.</span><span class="sxs-lookup"><span data-stu-id="4c687-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="4c687-109">—или—</span><span class="sxs-lookup"><span data-stu-id="4c687-109">—or—</span></span>  
  
-   <span data-ttu-id="4c687-110">Определите события в интерфейсе, используя `As` синтаксис и указать тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="4c687-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c687-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4c687-111">See Also</span></span>  
 [<span data-ttu-id="4c687-112">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="4c687-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="4c687-113">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="4c687-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="4c687-114">События</span><span class="sxs-lookup"><span data-stu-id="4c687-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
