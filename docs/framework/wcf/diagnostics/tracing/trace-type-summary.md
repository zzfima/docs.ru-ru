---
title: Сводка типов трассировок
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674840"
---
# <a name="trace-type-summary"></a><span data-ttu-id="a15f1-102">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="a15f1-102">Trace Type Summary</span></span>
<span data-ttu-id="a15f1-103">[Уровни исхода](xref:System.Diagnostics.SourceLevels) определяют различные уровни трассировки: критические, ошибочные, предупреждающие, информационные и verbose, а также предоставляют описание `ActivityTracing` флага, который переключает выход событий границы трассы и событий передачи активности.</span><span class="sxs-lookup"><span data-stu-id="a15f1-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="a15f1-104">Вы также <xref:System.Diagnostics.TraceEventType> можете просмотреть типы следов, которые <xref:System.Diagnostics>могут быть испущены из.</span><span class="sxs-lookup"><span data-stu-id="a15f1-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="a15f1-105">В следующей таблице перечислены наиболее важные из них.</span><span class="sxs-lookup"><span data-stu-id="a15f1-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="a15f1-106">Тип трассировки</span><span class="sxs-lookup"><span data-stu-id="a15f1-106">Trace Type</span></span>|<span data-ttu-id="a15f1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a15f1-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="a15f1-108">Critical</span><span class="sxs-lookup"><span data-stu-id="a15f1-108">Critical</span></span>|<span data-ttu-id="a15f1-109">Неустранимая ошибка или сбой в работе приложения.</span><span class="sxs-lookup"><span data-stu-id="a15f1-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="a15f1-110">Error</span><span class="sxs-lookup"><span data-stu-id="a15f1-110">Error</span></span>|<span data-ttu-id="a15f1-111">Устранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="a15f1-111">Recoverable error.</span></span>|  
|<span data-ttu-id="a15f1-112">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="a15f1-112">Warning</span></span>|<span data-ttu-id="a15f1-113">Информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="a15f1-113">Informational message.</span></span>|  
|<span data-ttu-id="a15f1-114">Сведения</span><span class="sxs-lookup"><span data-stu-id="a15f1-114">Information</span></span>|<span data-ttu-id="a15f1-115">Некритическая проблема.</span><span class="sxs-lookup"><span data-stu-id="a15f1-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="a15f1-116">Подробный</span><span class="sxs-lookup"><span data-stu-id="a15f1-116">Verbose</span></span>|<span data-ttu-id="a15f1-117">Трассировка отладки.</span><span class="sxs-lookup"><span data-stu-id="a15f1-117">Debugging trace.</span></span>|  
|<span data-ttu-id="a15f1-118">Запуск</span><span class="sxs-lookup"><span data-stu-id="a15f1-118">Start</span></span>|<span data-ttu-id="a15f1-119">Начало логического блока обработки.</span><span class="sxs-lookup"><span data-stu-id="a15f1-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a15f1-120">Приостановить</span><span class="sxs-lookup"><span data-stu-id="a15f1-120">Suspend</span></span>|<span data-ttu-id="a15f1-121">Приостановка логического блока обработки. </span><span class="sxs-lookup"><span data-stu-id="a15f1-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a15f1-122">Продолжить</span><span class="sxs-lookup"><span data-stu-id="a15f1-122">Resume</span></span>|<span data-ttu-id="a15f1-123">Возобновление логического блока обработки. </span><span class="sxs-lookup"><span data-stu-id="a15f1-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a15f1-124">Остановить</span><span class="sxs-lookup"><span data-stu-id="a15f1-124">Stop</span></span>|<span data-ttu-id="a15f1-125">Остановка логического блока обработки. </span><span class="sxs-lookup"><span data-stu-id="a15f1-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a15f1-126">Transfer</span><span class="sxs-lookup"><span data-stu-id="a15f1-126">Transfer</span></span>|<span data-ttu-id="a15f1-127">Изменение идентификации взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="a15f1-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="a15f1-128">Действие определяется как сочетание перечисленных выше типов трассировок.</span><span class="sxs-lookup"><span data-stu-id="a15f1-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="a15f1-129">Ниже приведено регулярное выражение, определяющее идеальное действие в локальной области (области источника трассировки):</span><span class="sxs-lookup"><span data-stu-id="a15f1-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="a15f1-130">Это означает, что действие должно удовлетворять следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="a15f1-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="a15f1-131">Должно запускаться и останавливаться трассировками Start и Stop соответственно.</span><span class="sxs-lookup"><span data-stu-id="a15f1-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="a15f1-132">Трассировка Transfer должна непосредственно предшествовать трассировке Suspend или Resume.</span><span class="sxs-lookup"><span data-stu-id="a15f1-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="a15f1-133">Не должно содержать никаких трассировок между трассировками Suspend и Resume, если такие трассировки имеются.</span><span class="sxs-lookup"><span data-stu-id="a15f1-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="a15f1-134">Может содержать любые и в любом количестве трассировки уровня Critical/Error/Warning/Information/Verbose/Transfer при условии соблюдения предыдущих условий.</span><span class="sxs-lookup"><span data-stu-id="a15f1-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="a15f1-135">Ниже приведено регулярное выражение, определяющее идеальное действие в глобальной области,</span><span class="sxs-lookup"><span data-stu-id="a15f1-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="a15f1-136">где R - регулярное выражение для действия в локальной области.</span><span class="sxs-lookup"><span data-stu-id="a15f1-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="a15f1-137">Таким образом, получаем:</span><span class="sxs-lookup"><span data-stu-id="a15f1-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
