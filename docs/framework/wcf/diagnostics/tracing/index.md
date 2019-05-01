---
title: Трассировка
ms.date: 03/30/2017
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
ms.openlocfilehash: 2379b290494e72b65db5ddc6a7bc5df376d4373f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997990"
---
# <a name="tracing"></a><span data-ttu-id="6a76e-102">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6a76e-102">Tracing</span></span>
<span data-ttu-id="6a76e-103">Windows Communication Foundation (WCF) предоставляет данные инструментирования приложений и диагностических данных для мониторинга и анализа сбоев.</span><span class="sxs-lookup"><span data-stu-id="6a76e-103">Windows Communication Foundation (WCF) provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="6a76e-104">Трассировку можно использовать вместо отладчика для понимания того, как ведет себя приложение или почему оно дает сбои.</span><span class="sxs-lookup"><span data-stu-id="6a76e-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="6a76e-105">Можно также устанавливать корреляцию между сбоями и обработкой, выполняемой различными компонентами, для сквозного анализа работы приложения.</span><span class="sxs-lookup"><span data-stu-id="6a76e-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 <span data-ttu-id="6a76e-106">WCF выводит следующие данные для диагностической трассировки:</span><span class="sxs-lookup"><span data-stu-id="6a76e-106">WCF outputs the following data for diagnostic tracing:</span></span>  
  
- <span data-ttu-id="6a76e-107">Трассировки основных этапов процесса по всем компонентам приложений, таких как вызовы операций, исключения кода, предупреждения и прочие значительные события обработки.</span><span class="sxs-lookup"><span data-stu-id="6a76e-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
- <span data-ttu-id="6a76e-108">События ошибок Windows при сбоях возможности трассировки.</span><span class="sxs-lookup"><span data-stu-id="6a76e-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a76e-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6a76e-109">In This Section</span></span>  
 [<span data-ttu-id="6a76e-110">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="6a76e-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="6a76e-111">В этом разделе описывается, как настраивать трассировку на разных уровнях в соответствии с конкретными потребностями.</span><span class="sxs-lookup"><span data-stu-id="6a76e-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="6a76e-112">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="6a76e-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="6a76e-113">В этом разделе описывается использование распространения и трассировки действий для сквозной корреляции, полезной при отладке.</span><span class="sxs-lookup"><span data-stu-id="6a76e-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="6a76e-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6a76e-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="6a76e-115">В этом разделе описывается использование трассировки для отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="6a76e-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="6a76e-116">Проблемы безопасности и полезные советы при трассировке</span><span class="sxs-lookup"><span data-stu-id="6a76e-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="6a76e-117">В этом разделе описываются способы защиты конфиденциальных сведений от раскрытия, а также приводятся полезные советы по использованию WebHost.</span><span class="sxs-lookup"><span data-stu-id="6a76e-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="6a76e-118">Справочные сведения о трассировке</span><span class="sxs-lookup"><span data-stu-id="6a76e-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="6a76e-119">В этом разделе перечислены все трассировки, генерируемые WCF.</span><span class="sxs-lookup"><span data-stu-id="6a76e-119">This topic lists all the traces generated by WCF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a76e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6a76e-120">See also</span></span>

- [<span data-ttu-id="6a76e-121">Средство просмотра трассировки служб (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="6a76e-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
