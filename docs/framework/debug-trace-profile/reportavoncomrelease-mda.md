---
title: Помощник по отладке управляемого кода reportAvOnComRelease
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0ecb05dba70dc9c8aba7f04928fd0ab49c900c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125584"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="a27b7-102">Помощник по отладке управляемого кода reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="a27b7-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="a27b7-103">Помощник отладки управляемого кода (MDA) `reportAvOnComRelease` активируется при возникновении исключений, вызванных ошибками подсчета пользовательских ссылок при выполнении COM-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.</span><span class="sxs-lookup"><span data-stu-id="a27b7-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a27b7-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="a27b7-104">Symptoms</span></span>  
 <span data-ttu-id="a27b7-105">Нарушения прав доступа и повреждение памяти.</span><span class="sxs-lookup"><span data-stu-id="a27b7-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a27b7-106">Причина</span><span class="sxs-lookup"><span data-stu-id="a27b7-106">Cause</span></span>  
 <span data-ttu-id="a27b7-107">Иногда исключение возникает в связи с ошибками подсчета пользовательских ссылок при выполнении COM-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.</span><span class="sxs-lookup"><span data-stu-id="a27b7-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="a27b7-108">Обычно это исключение отменяется, так как в противном случае в среде CLR произойдет нарушение прав доступа, и работа среды будет завершена.</span><span class="sxs-lookup"><span data-stu-id="a27b7-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="a27b7-109">Когда этот помощник включен, такие исключения вместо простой отмены можно обнаруживать и выводить в отчетах.</span><span class="sxs-lookup"><span data-stu-id="a27b7-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a27b7-110">Решение</span><span class="sxs-lookup"><span data-stu-id="a27b7-110">Resolution</span></span>  
 <span data-ttu-id="a27b7-111">Изучите свой код подсчета ссылок для поиска ошибок и проверки собственных клиентов объекта на наличие ошибок подсчета ссылок.</span><span class="sxs-lookup"><span data-stu-id="a27b7-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a27b7-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="a27b7-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="a27b7-113">Доступно два режима.</span><span class="sxs-lookup"><span data-stu-id="a27b7-113">Two modes are available.</span></span> <span data-ttu-id="a27b7-114">Если атрибут `allowAv` имеет значение `true`, помощник запрещает среде выполнения отменить нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="a27b7-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="a27b7-115">Если `allowAv` имеет значение `false`, которое используется по умолчанию, среды выполнения отменяет нарушение прав доступа, однако пользователь получает предупреждение о возникновении и отмене исключения.</span><span class="sxs-lookup"><span data-stu-id="a27b7-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a27b7-116">Вывод</span><span class="sxs-lookup"><span data-stu-id="a27b7-116">Output</span></span>  
 <span data-ttu-id="a27b7-117">Когда это возможно, выходные данные содержат исходный vtable указателя интерфейса COM.</span><span class="sxs-lookup"><span data-stu-id="a27b7-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="a27b7-118">В противном случае отображается информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="a27b7-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a27b7-119">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="a27b7-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a27b7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a27b7-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a27b7-121">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="a27b7-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a27b7-122">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="a27b7-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
