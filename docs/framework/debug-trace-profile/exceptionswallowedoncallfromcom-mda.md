---
title: exceptionSwallowedOnCallFromCom MDA
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f076cbc556c7d9feff8a226f050743cd7728622
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148152"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="a7c84-102">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="a7c84-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="a7c84-103">Помощник отладки управляемого кода (MDA) `exceptionSwallowedOnCallFromCOM` активируется при возникновении исключения из кода среды CLR, вызываемого из COM посредством метода, который не имеет неуправляемого типа возвращаемого значения HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a7c84-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a7c84-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="a7c84-104">Symptoms</span></span>  
 <span data-ttu-id="a7c84-105">Вызов управляемого компонента из COM возвращает значение FALSE или 0.</span><span class="sxs-lookup"><span data-stu-id="a7c84-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="a7c84-106">Кроме того, если метод имеет тип возвращаемого значения void, указание на возникновение исключения во время выполнения метода может отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="a7c84-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="a7c84-107">В этом случае исключение будет перехвачено без предупреждения и возвращено вызывающему объекту COM.</span><span class="sxs-lookup"><span data-stu-id="a7c84-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a7c84-108">Причина</span><span class="sxs-lookup"><span data-stu-id="a7c84-108">Cause</span></span>  
 <span data-ttu-id="a7c84-109">Возникло исключение, однако не существует приемлемого способа сообщить об этом.</span><span class="sxs-lookup"><span data-stu-id="a7c84-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a7c84-110">Решение</span><span class="sxs-lookup"><span data-stu-id="a7c84-110">Resolution</span></span>  
 <span data-ttu-id="a7c84-111">Сведения приведены исключительно для справки и необязательно указывают на наличие ошибки.</span><span class="sxs-lookup"><span data-stu-id="a7c84-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a7c84-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="a7c84-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="a7c84-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="a7c84-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="a7c84-114">Он только выводит данные об исключениях, перехваченных без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="a7c84-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a7c84-115">Вывод</span><span class="sxs-lookup"><span data-stu-id="a7c84-115">Output</span></span>  
 <span data-ttu-id="a7c84-116">Информационное сообщение с именем метода, именем типа и указанием на исключение.</span><span class="sxs-lookup"><span data-stu-id="a7c84-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a7c84-117">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="a7c84-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7c84-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a7c84-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a7c84-119">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="a7c84-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a7c84-120">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="a7c84-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
