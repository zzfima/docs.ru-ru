---
title: "Уменьшение: вызовы метода EventSource.WriteEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 270f89183bced5d07598b1731f18acf90ec9715a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a><span data-ttu-id="0b64f-102">Уменьшение: вызовы метода EventSource.WriteEvent</span><span class="sxs-lookup"><span data-stu-id="0b64f-102">Mitigation: EventSource.WriteEvent Method Calls</span></span>
<span data-ttu-id="0b64f-103">В [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] реализуется контракт между методом событий ETW в классе, производном от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> , и методом <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> его базового класса.</span><span class="sxs-lookup"><span data-stu-id="0b64f-103">The [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] enforces a contract between an ETW event method in a class that is derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> and  the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method of its base class.</span></span> <span data-ttu-id="0b64f-104">Метод событий ETW должен передавать метод <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> и идентификатор события с теми же аргументами, которые были переданы в метод событий.</span><span class="sxs-lookup"><span data-stu-id="0b64f-104">The ETW event method must pass the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method the event ID followed by the same arguments that were passed to the event method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="0b64f-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="0b64f-105">Impact</span></span>  
 <span data-ttu-id="0b64f-106">Метод событий ETW, определенный следующим образом, нарушает контракт.</span><span class="sxs-lookup"><span data-stu-id="0b64f-106">An ETW event method defined in the following way breaks the contract:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
```  
  
 <span data-ttu-id="0b64f-107">Если этот контракт нарушен, во время выполнения возникает исключение <xref:System.IndexOutOfRangeException> , если объект <xref:System.Diagnostics.Tracing.EventListener> считывает данные <xref:System.Diagnostics.Tracing.EventSource> в процессе.</span><span class="sxs-lookup"><span data-stu-id="0b64f-107">When this contract is violated, an <xref:System.IndexOutOfRangeException> exception is thrown at run time if an <xref:System.Diagnostics.Tracing.EventListener> object reads <xref:System.Diagnostics.Tracing.EventSource> data in process.</span></span>  
  
 <span data-ttu-id="0b64f-108">Определение этого метода событий ETW должно иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="0b64f-108">The definition for this ETW event method should follow this pattern:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
```  
  
## <a name="mitigation"></a><span data-ttu-id="0b64f-109">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="0b64f-109">Mitigation</span></span>  
 <span data-ttu-id="0b64f-110">Для соответствия требуемому виду необходимо изменить существующий код.</span><span class="sxs-lookup"><span data-stu-id="0b64f-110">You must modify existing code to conform to the required pattern.</span></span>  
  
 <span data-ttu-id="0b64f-111">Можно минимизировать объем кода, который необходимо изменить, указав два метода для вызова метода <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0b64f-111">You can minimize the amount of code that you have to change by defining two methods for calling the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method, as follows:</span></span>  
  
```  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b64f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0b64f-112">See Also</span></span>  
 [<span data-ttu-id="0b64f-113">Изменения среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0b64f-113">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

