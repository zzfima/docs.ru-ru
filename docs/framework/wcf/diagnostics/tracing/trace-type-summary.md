---
title: Сводка типов трассировок
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856009"
---
# <a name="trace-type-summary"></a><span data-ttu-id="3d86a-102">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="3d86a-102">Trace Type Summary</span></span>
<span data-ttu-id="3d86a-103">[Уровни источника](https://go.microsoft.com/fwlink/?LinkID=94943) определяют различные уровни трассировки: Критическая, ошибка, предупреждение, информация и подробные сведения, а также описание `ActivityTracing` флага, который переключает выходные данные границ трассировки и событий перемещения действий.</span><span class="sxs-lookup"><span data-stu-id="3d86a-103">[Source Levels](https://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="3d86a-104">Можно также проверить [трацеевенттипе](https://go.microsoft.com/fwlink/?LinkId=95169) для типов трассировок, которые могут быть выпущены из <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="3d86a-104">You can also review [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="3d86a-105">В следующей таблице перечислены наиболее важные из них.</span><span class="sxs-lookup"><span data-stu-id="3d86a-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="3d86a-106">Тип трассировки</span><span class="sxs-lookup"><span data-stu-id="3d86a-106">Trace Type</span></span>|<span data-ttu-id="3d86a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3d86a-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="3d86a-108">Critical</span><span class="sxs-lookup"><span data-stu-id="3d86a-108">Critical</span></span>|<span data-ttu-id="3d86a-109">Неустранимая ошибка или сбой в работе приложения.</span><span class="sxs-lookup"><span data-stu-id="3d86a-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="3d86a-110">Ошибка</span><span class="sxs-lookup"><span data-stu-id="3d86a-110">Error</span></span>|<span data-ttu-id="3d86a-111">Устранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3d86a-111">Recoverable error.</span></span>|  
|<span data-ttu-id="3d86a-112">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="3d86a-112">Warning</span></span>|<span data-ttu-id="3d86a-113">Информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="3d86a-113">Informational message.</span></span>|  
|<span data-ttu-id="3d86a-114">Сведения</span><span class="sxs-lookup"><span data-stu-id="3d86a-114">Information</span></span>|<span data-ttu-id="3d86a-115">Некритическая проблема.</span><span class="sxs-lookup"><span data-stu-id="3d86a-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="3d86a-116">Verbose</span><span class="sxs-lookup"><span data-stu-id="3d86a-116">Verbose</span></span>|<span data-ttu-id="3d86a-117">Отладка трассировки.</span><span class="sxs-lookup"><span data-stu-id="3d86a-117">Debugging trace.</span></span>|  
|<span data-ttu-id="3d86a-118">Запуск</span><span class="sxs-lookup"><span data-stu-id="3d86a-118">Start</span></span>|<span data-ttu-id="3d86a-119">Начало логического блока обработки.</span><span class="sxs-lookup"><span data-stu-id="3d86a-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="3d86a-120">Suspend</span><span class="sxs-lookup"><span data-stu-id="3d86a-120">Suspend</span></span>|<span data-ttu-id="3d86a-121">Приостановка логической единицы обработки.</span><span class="sxs-lookup"><span data-stu-id="3d86a-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="3d86a-122">Возобновление</span><span class="sxs-lookup"><span data-stu-id="3d86a-122">Resume</span></span>|<span data-ttu-id="3d86a-123">Возобновление логической единицы обработки.</span><span class="sxs-lookup"><span data-stu-id="3d86a-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="3d86a-124">Остановить</span><span class="sxs-lookup"><span data-stu-id="3d86a-124">Stop</span></span>|<span data-ttu-id="3d86a-125">Остановка логической единицы обработки.</span><span class="sxs-lookup"><span data-stu-id="3d86a-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="3d86a-126">Transfer</span><span class="sxs-lookup"><span data-stu-id="3d86a-126">Transfer</span></span>|<span data-ttu-id="3d86a-127">Изменение удостоверения корреляции.</span><span class="sxs-lookup"><span data-stu-id="3d86a-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="3d86a-128">Действие определяется как сочетание перечисленных выше типов трассировок.</span><span class="sxs-lookup"><span data-stu-id="3d86a-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="3d86a-129">Ниже приведено регулярное выражение, определяющее идеальное действие в локальной области (области источника трассировки):</span><span class="sxs-lookup"><span data-stu-id="3d86a-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="3d86a-130">Это означает, что действие должно удовлетворять следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="3d86a-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="3d86a-131">Должно запускаться и останавливаться трассировками Start и Stop соответственно.</span><span class="sxs-lookup"><span data-stu-id="3d86a-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="3d86a-132">Трассировка Transfer должна непосредственно предшествовать трассировке Suspend или Resume.</span><span class="sxs-lookup"><span data-stu-id="3d86a-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="3d86a-133">Не должно содержать никаких трассировок между трассировками Suspend и Resume, если такие трассировки имеются.</span><span class="sxs-lookup"><span data-stu-id="3d86a-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="3d86a-134">Может содержать любые и в любом количестве трассировки уровня Critical/Error/Warning/Information/Verbose/Transfer при условии соблюдения предыдущих условий.</span><span class="sxs-lookup"><span data-stu-id="3d86a-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="3d86a-135">Ниже приведено регулярное выражение, определяющее идеальное действие в глобальной области,</span><span class="sxs-lookup"><span data-stu-id="3d86a-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="3d86a-136">где R - регулярное выражение для действия в локальной области.</span><span class="sxs-lookup"><span data-stu-id="3d86a-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="3d86a-137">Таким образом, получаем:</span><span class="sxs-lookup"><span data-stu-id="3d86a-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
