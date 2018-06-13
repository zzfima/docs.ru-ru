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
ms.openlocfilehash: b4c1cbf075ef96073061679b6d062075490f5e4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390612"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="9df9e-102">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="9df9e-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="9df9e-103">Помощник отладки управляемого кода (MDA) `exceptionSwallowedOnCallFromCOM` активируется при возникновении исключения из кода среды CLR, вызываемого из COM посредством метода, который не имеет неуправляемого типа возвращаемого значения HRESULT.</span><span class="sxs-lookup"><span data-stu-id="9df9e-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9df9e-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="9df9e-104">Symptoms</span></span>  
 <span data-ttu-id="9df9e-105">Вызов управляемого компонента из COM возвращает значение FALSE или 0.</span><span class="sxs-lookup"><span data-stu-id="9df9e-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="9df9e-106">Кроме того, если метод имеет тип возвращаемого значения void, указание на возникновение исключения во время выполнения метода может отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="9df9e-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="9df9e-107">В этом случае исключение будет перехвачено без предупреждения и возвращено вызывающему объекту COM.</span><span class="sxs-lookup"><span data-stu-id="9df9e-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9df9e-108">Причина</span><span class="sxs-lookup"><span data-stu-id="9df9e-108">Cause</span></span>  
 <span data-ttu-id="9df9e-109">Возникло исключение, однако не существует приемлемого способа сообщить об этом.</span><span class="sxs-lookup"><span data-stu-id="9df9e-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9df9e-110">Решение</span><span class="sxs-lookup"><span data-stu-id="9df9e-110">Resolution</span></span>  
 <span data-ttu-id="9df9e-111">Сведения приведены исключительно для справки и необязательно указывают на наличие ошибки.</span><span class="sxs-lookup"><span data-stu-id="9df9e-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9df9e-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="9df9e-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="9df9e-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="9df9e-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="9df9e-114">Он только выводит данные об исключениях, перехваченных без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="9df9e-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9df9e-115">Вывод</span><span class="sxs-lookup"><span data-stu-id="9df9e-115">Output</span></span>  
 <span data-ttu-id="9df9e-116">Информационное сообщение с именем метода, именем типа и указанием на исключение.</span><span class="sxs-lookup"><span data-stu-id="9df9e-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9df9e-117">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="9df9e-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9df9e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9df9e-118">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="9df9e-119">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="9df9e-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="9df9e-120">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9df9e-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
