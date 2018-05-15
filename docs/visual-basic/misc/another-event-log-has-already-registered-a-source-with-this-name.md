---
title: Другой журнал событий уже зарегистрировал источник с таким именем
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: b12fd5dcdeaccb0dc294c44e4b8a898726978633
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="d0581-102">Другой журнал событий уже зарегистрировал источник с таким именем</span><span class="sxs-lookup"><span data-stu-id="d0581-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="d0581-103">Предпринята попытка выполнить запись в журнал событий, когда указанный источник уже зарегистрирован другим журналом событий.</span><span class="sxs-lookup"><span data-stu-id="d0581-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="d0581-104">Перед внесением компонента записи в журнал необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> вашего экземпляра компонента <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="d0581-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="d0581-105">В этом случае система проверяет, что указанный источник зарегистрирован в журнале событий, в который компонент осуществляет запись, и при необходимости вызывает <xref:System.Diagnostics.EventLog.CreateEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="d0581-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0581-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d0581-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d0581-107">Удалите связь источника с первым журналом с помощью метода <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> или <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="d0581-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="d0581-108">Зарегистрируйте источник для нового журнала.</span><span class="sxs-lookup"><span data-stu-id="d0581-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0581-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d0581-109">See Also</span></span>  
 [<span data-ttu-id="d0581-110">Объект My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="d0581-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  

