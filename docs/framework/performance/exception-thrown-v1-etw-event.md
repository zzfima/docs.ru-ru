---
title: Событие ExceptionThrown_V1 (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07932a12916138dd7cbee2576e4fc747898b8063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610855"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="6341a-102">Событие ExceptionThrown_V1 (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="6341a-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="6341a-103">Это событие захватывает информацию о вызванных исключениях.</span><span class="sxs-lookup"><span data-stu-id="6341a-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="6341a-104">В следующей таблице показаны ключевое слово, в котором вызывается событие, и уровень события.</span><span class="sxs-lookup"><span data-stu-id="6341a-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="6341a-105">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="6341a-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6341a-106">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6341a-106">Keyword for raising the event</span></span>|<span data-ttu-id="6341a-107">Уровень</span><span class="sxs-lookup"><span data-stu-id="6341a-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6341a-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="6341a-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="6341a-109">Предупреждение (2)</span><span class="sxs-lookup"><span data-stu-id="6341a-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="6341a-110">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6341a-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="6341a-111">событие</span><span class="sxs-lookup"><span data-stu-id="6341a-111">Event</span></span>|<span data-ttu-id="6341a-112">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6341a-112">Event ID</span></span>|<span data-ttu-id="6341a-113">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6341a-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="6341a-114">80</span><span class="sxs-lookup"><span data-stu-id="6341a-114">80</span></span>|<span data-ttu-id="6341a-115">Возникло управляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="6341a-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="6341a-116">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6341a-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="6341a-117">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6341a-117">Field name</span></span>|<span data-ttu-id="6341a-118">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6341a-118">Data type</span></span>|<span data-ttu-id="6341a-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="6341a-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6341a-120">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="6341a-120">Exception Type</span></span>|<span data-ttu-id="6341a-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6341a-121">win:UnicodeString</span></span>|<span data-ttu-id="6341a-122">Тип исключения, например `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="6341a-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="6341a-123">Сообщение об исключении</span><span class="sxs-lookup"><span data-stu-id="6341a-123">Exception Message</span></span>|<span data-ttu-id="6341a-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6341a-124">win:UnicodeString</span></span>|<span data-ttu-id="6341a-125">Фактическое сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="6341a-125">Actual exception message.</span></span>|  
|<span data-ttu-id="6341a-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="6341a-126">EIPCodeThrow</span></span>|<span data-ttu-id="6341a-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="6341a-127">win:Pointer</span></span>|<span data-ttu-id="6341a-128">Указатель на инструкцию, в которой возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="6341a-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="6341a-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="6341a-129">ExceptionHR</span></span>|<span data-ttu-id="6341a-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6341a-130">win:UInt32</span></span>|<span data-ttu-id="6341a-131">Исключение [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span><span class="sxs-lookup"><span data-stu-id="6341a-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="6341a-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="6341a-132">ExceptionFlags</span></span>|<span data-ttu-id="6341a-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6341a-133">win:UInt16</span></span>|<span data-ttu-id="6341a-134">0x01: HasInnerException (см. в разделе [события трассировки событий Windows среды CLR](../../../docs/framework/performance/clr-etw-events.md) в документации по Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6341a-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="6341a-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="6341a-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="6341a-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="6341a-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="6341a-137">0x08: IsCorruptedStateException (указывает, что процесс находится в поврежденном состоянии, см. в разделе [обработка исключений поврежденного состояния](https://go.microsoft.com/fwlink/?LinkId=179681) на сайте MSDN).</span><span class="sxs-lookup"><span data-stu-id="6341a-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="6341a-138">0x10: IsCLSCompliant (исключение, которое является производным от <xref:System.Exception> является CLS-совместимым; в противном случае он не является CLS-совместимым).</span><span class="sxs-lookup"><span data-stu-id="6341a-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="6341a-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6341a-139">ClrInstanceID</span></span>|<span data-ttu-id="6341a-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6341a-140">win:UInt16</span></span>|<span data-ttu-id="6341a-141">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6341a-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6341a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="6341a-142">See also</span></span>
- [<span data-ttu-id="6341a-143">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="6341a-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
