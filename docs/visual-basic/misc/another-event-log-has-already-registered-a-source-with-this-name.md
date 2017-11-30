---
title: "Другой журнал событий уже зарегистрировал источник с таким именем"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="e69cb-102">Другой журнал событий уже зарегистрировал источник с таким именем</span><span class="sxs-lookup"><span data-stu-id="e69cb-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="e69cb-103">Предпринята попытка выполнить запись в журнал событий, когда указанный источник уже зарегистрирован другим журналом событий.</span><span class="sxs-lookup"><span data-stu-id="e69cb-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="e69cb-104">Перед внесением компонента записи в журнал необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> вашего экземпляра компонента <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="e69cb-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="e69cb-105">В этом случае система проверяет, что указанный источник зарегистрирован в журнале событий, в который компонент осуществляет запись, и при необходимости вызывает <xref:System.Diagnostics.EventLog.CreateEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="e69cb-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e69cb-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e69cb-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="e69cb-107">Удалите связь источника с первым журналом с помощью метода <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> или <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="e69cb-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="e69cb-108">Зарегистрируйте источник для нового журнала.</span><span class="sxs-lookup"><span data-stu-id="e69cb-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69cb-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e69cb-109">See Also</span></span>  
 [<span data-ttu-id="e69cb-110">Объект My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="e69cb-110">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="e69cb-111">Как: удалить источник событий</span><span class="sxs-lookup"><span data-stu-id="e69cb-111">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [<span data-ttu-id="e69cb-112">Способ: добавить приложение в качестве источника записей журнала событий</span><span class="sxs-lookup"><span data-stu-id="e69cb-112">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
