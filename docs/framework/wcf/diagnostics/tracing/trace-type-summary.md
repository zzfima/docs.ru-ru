---
title: Сводка типов трассировок
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e3bc66753dd44e1dc4c7417caf593820300f69a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="trace-type-summary"></a><span data-ttu-id="85389-102">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="85389-102">Trace Type Summary</span></span>
<span data-ttu-id="85389-103">[Уровни источника](http://go.microsoft.com/fwlink/?LinkID=94943) определяются различные уровни трассировки: критическое, ошибка, предупреждение, сведения и подробные сведения, а также приводится описание `ActivityTracing` границ и действие передачи событий трассировки флага, которые выводом.</span><span class="sxs-lookup"><span data-stu-id="85389-103">[Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="85389-104">Можно также просмотреть [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) для типов трассировок, которые могут выдаваться в <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="85389-104">You can also review [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="85389-105">В следующей таблице перечислены наиболее важные из них.</span><span class="sxs-lookup"><span data-stu-id="85389-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="85389-106">Тип трассировки</span><span class="sxs-lookup"><span data-stu-id="85389-106">Trace Type</span></span>|<span data-ttu-id="85389-107">Описание</span><span class="sxs-lookup"><span data-stu-id="85389-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="85389-108">Critical</span><span class="sxs-lookup"><span data-stu-id="85389-108">Critical</span></span>|<span data-ttu-id="85389-109">Неустранимая ошибка или сбой в работе приложения.</span><span class="sxs-lookup"><span data-stu-id="85389-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="85389-110">Ошибка</span><span class="sxs-lookup"><span data-stu-id="85389-110">Error</span></span>|<span data-ttu-id="85389-111">Устранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="85389-111">Recoverable error.</span></span>|  
|<span data-ttu-id="85389-112">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="85389-112">Warning</span></span>|<span data-ttu-id="85389-113">Информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="85389-113">Informational message.</span></span>|  
|<span data-ttu-id="85389-114">Сведения</span><span class="sxs-lookup"><span data-stu-id="85389-114">Information</span></span>|<span data-ttu-id="85389-115">Некритическая ошибка.</span><span class="sxs-lookup"><span data-stu-id="85389-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="85389-116">Verbose</span><span class="sxs-lookup"><span data-stu-id="85389-116">Verbose</span></span>|<span data-ttu-id="85389-117">Трассировка отладки.</span><span class="sxs-lookup"><span data-stu-id="85389-117">Debugging trace.</span></span>|  
|<span data-ttu-id="85389-118">Запуск</span><span class="sxs-lookup"><span data-stu-id="85389-118">Start</span></span>|<span data-ttu-id="85389-119">Начало логического блока обработки.</span><span class="sxs-lookup"><span data-stu-id="85389-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="85389-120">Suspend</span><span class="sxs-lookup"><span data-stu-id="85389-120">Suspend</span></span>|<span data-ttu-id="85389-121">Приостановка обработки логическую единицу.</span><span class="sxs-lookup"><span data-stu-id="85389-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="85389-122">возобновление</span><span class="sxs-lookup"><span data-stu-id="85389-122">Resume</span></span>|<span data-ttu-id="85389-123">Возобновление логический блок обработки.</span><span class="sxs-lookup"><span data-stu-id="85389-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="85389-124">Остановить</span><span class="sxs-lookup"><span data-stu-id="85389-124">Stop</span></span>|<span data-ttu-id="85389-125">Остановка логический блок обработки.</span><span class="sxs-lookup"><span data-stu-id="85389-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="85389-126">Transfer</span><span class="sxs-lookup"><span data-stu-id="85389-126">Transfer</span></span>|<span data-ttu-id="85389-127">Изменение идентификации взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="85389-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="85389-128">Действие определяется как сочетание перечисленных выше типов трассировок.</span><span class="sxs-lookup"><span data-stu-id="85389-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="85389-129">Ниже приведено регулярное выражение, определяющее идеальное действие в локальной области (области источника трассировки):</span><span class="sxs-lookup"><span data-stu-id="85389-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="85389-130">Это означает, что действие должно удовлетворять следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="85389-130">This means that an activity must satisfy the following conditions.</span></span>  
  
-   <span data-ttu-id="85389-131">Должно запускаться и останавливаться трассировками Start и Stop соответственно.</span><span class="sxs-lookup"><span data-stu-id="85389-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
-   <span data-ttu-id="85389-132">Трассировка Transfer должна непосредственно предшествовать трассировке Suspend или Resume.</span><span class="sxs-lookup"><span data-stu-id="85389-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
-   <span data-ttu-id="85389-133">Не должно содержать никаких трассировок между трассировками Suspend и Resume, если такие трассировки имеются.</span><span class="sxs-lookup"><span data-stu-id="85389-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
-   <span data-ttu-id="85389-134">Может содержать любые и в любом количестве трассировки уровня Critical/Error/Warning/Information/Verbose/Transfer при условии соблюдения предыдущих условий.</span><span class="sxs-lookup"><span data-stu-id="85389-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="85389-135">Ниже приведено регулярное выражение, определяющее идеальное действие в глобальной области,</span><span class="sxs-lookup"><span data-stu-id="85389-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="85389-136">где R - регулярное выражение для действия в локальной области.</span><span class="sxs-lookup"><span data-stu-id="85389-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="85389-137">Таким образом, получаем:</span><span class="sxs-lookup"><span data-stu-id="85389-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
