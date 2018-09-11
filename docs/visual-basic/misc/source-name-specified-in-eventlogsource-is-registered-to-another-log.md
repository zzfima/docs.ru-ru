---
title: Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 03fcc41b0fbb84233aa037d7af17d168050a98b6
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261055"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="ed93d-102">Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName</span><span class="sxs-lookup"><span data-stu-id="ed93d-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="ed93d-103">`EventLog` пытается сослаться на источник, который зарегистрирован в другом журнале.</span><span class="sxs-lookup"><span data-stu-id="ed93d-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="ed93d-104">Для добавления записей в журнал событий необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> .</span><span class="sxs-lookup"><span data-stu-id="ed93d-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="ed93d-105">Свойство <xref:System.Diagnostics.EventLog.Source%2A> регистрирует компонент в журнале событий в качестве допустимого источника записей.</span><span class="sxs-lookup"><span data-stu-id="ed93d-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="ed93d-106">Один источник может быть связан только с одним журналом событий одновременно (и поэтому может добавлять записи только в него).</span><span class="sxs-lookup"><span data-stu-id="ed93d-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="ed93d-107">По умолчанию при попытке добавить запись в журнал без предварительной регистрации компонента в качестве разрешенного источника система автоматически регистрирует его в этом журнале, используя значение свойства <xref:System.Diagnostics.EventLog.Source%2A> в качестве строки источника.</span><span class="sxs-lookup"><span data-stu-id="ed93d-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed93d-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ed93d-108">To correct this error</span></span>  
  
-   <span data-ttu-id="ed93d-109">Убедитесь в том, что источник зарегистрирован в соответствующем журнале.</span><span class="sxs-lookup"><span data-stu-id="ed93d-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="ed93d-110">Для этого используйте метод <xref:System.Diagnostics.EventLog.CreateEventSource%2A> или одну из его перегрузок, чтобы указать строку, однозначно идентифицирующую компонент в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="ed93d-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed93d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ed93d-111">See Also</span></span>  
 [<span data-ttu-id="ed93d-112">Администрирование журнала событий</span><span class="sxs-lookup"><span data-stu-id="ed93d-112">Administering Event Logs</span></span>](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [<span data-ttu-id="ed93d-113">Ссылки на журнал событий</span><span class="sxs-lookup"><span data-stu-id="ed93d-113">Event Log References</span></span>](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [<span data-ttu-id="ed93d-114">Практическое: добавьте приложение в качестве источника записей журнала событий</span><span class="sxs-lookup"><span data-stu-id="ed93d-114">How to: Add Your Application as a Source of Event Log Entries</span></span>](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [<span data-ttu-id="ed93d-115">Практическое: удалить источник событий</span><span class="sxs-lookup"><span data-stu-id="ed93d-115">How to: Remove an Event Source</span></span>](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
