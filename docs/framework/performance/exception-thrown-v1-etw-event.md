---
title: "Событие ExceptionThrown_V1 (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dcf3390821c4210ced4c43dab5a94c93802d5f9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="4eacb-102">Событие ExceptionThrown_V1 (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="4eacb-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="4eacb-103">Это событие захватывает информацию о вызванных исключениях.</span><span class="sxs-lookup"><span data-stu-id="4eacb-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="4eacb-104">В следующей таблице показаны ключевое слово, в котором вызывается событие, и уровень события.</span><span class="sxs-lookup"><span data-stu-id="4eacb-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="4eacb-105">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="4eacb-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="4eacb-106">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="4eacb-106">Keyword for raising the event</span></span>|<span data-ttu-id="4eacb-107">Уровень</span><span class="sxs-lookup"><span data-stu-id="4eacb-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4eacb-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="4eacb-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="4eacb-109">Предупреждение (2)</span><span class="sxs-lookup"><span data-stu-id="4eacb-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="4eacb-110">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="4eacb-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="4eacb-111">Событие</span><span class="sxs-lookup"><span data-stu-id="4eacb-111">Event</span></span>|<span data-ttu-id="4eacb-112">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4eacb-112">Event ID</span></span>|<span data-ttu-id="4eacb-113">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="4eacb-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="4eacb-114">80</span><span class="sxs-lookup"><span data-stu-id="4eacb-114">80</span></span>|<span data-ttu-id="4eacb-115">Возникло управляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="4eacb-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="4eacb-116">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="4eacb-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="4eacb-117">Имя поля</span><span class="sxs-lookup"><span data-stu-id="4eacb-117">Field name</span></span>|<span data-ttu-id="4eacb-118">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4eacb-118">Data type</span></span>|<span data-ttu-id="4eacb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4eacb-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4eacb-120">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="4eacb-120">Exception Type</span></span>|<span data-ttu-id="4eacb-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4eacb-121">win:UnicodeString</span></span>|<span data-ttu-id="4eacb-122">Тип исключения, например `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="4eacb-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="4eacb-123">Сообщение об исключении</span><span class="sxs-lookup"><span data-stu-id="4eacb-123">Exception Message</span></span>|<span data-ttu-id="4eacb-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4eacb-124">win:UnicodeString</span></span>|<span data-ttu-id="4eacb-125">Фактическое сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="4eacb-125">Actual exception message.</span></span>|  
|<span data-ttu-id="4eacb-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="4eacb-126">EIPCodeThrow</span></span>|<span data-ttu-id="4eacb-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4eacb-127">win:Pointer</span></span>|<span data-ttu-id="4eacb-128">Указатель на инструкцию, в которой возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="4eacb-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="4eacb-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="4eacb-129">ExceptionHR</span></span>|<span data-ttu-id="4eacb-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4eacb-130">win:UInt32</span></span>|<span data-ttu-id="4eacb-131">Исключение [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).</span><span class="sxs-lookup"><span data-stu-id="4eacb-131">Exception [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="4eacb-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="4eacb-132">ExceptionFlags</span></span>|<span data-ttu-id="4eacb-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4eacb-133">win:UInt16</span></span>|<span data-ttu-id="4eacb-134">0x01: HasInnerException (см. раздел [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md) в документации по Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4eacb-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="4eacb-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="4eacb-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="4eacb-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="4eacb-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="4eacb-137">0x08: IsCorruptedStateException (указывает, что процесс находится в поврежденном состоянии, см. раздел [Обработка исключений поврежденного состояния](http://go.microsoft.com/fwlink/?LinkId=179681) в библиотеке MSDN).</span><span class="sxs-lookup"><span data-stu-id="4eacb-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](http://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="4eacb-138">0x10: IsCLSCompliant (исключение, производное от <xref:System.Exception>, является CLS-совместимым; в противном случае такое исключение не является CLS-совместимым).</span><span class="sxs-lookup"><span data-stu-id="4eacb-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="4eacb-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4eacb-139">ClrInstanceID</span></span>|<span data-ttu-id="4eacb-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4eacb-140">win:UInt16</span></span>|<span data-ttu-id="4eacb-141">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4eacb-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4eacb-142">См. также</span><span class="sxs-lookup"><span data-stu-id="4eacb-142">See Also</span></span>  
 [<span data-ttu-id="4eacb-143">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="4eacb-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
