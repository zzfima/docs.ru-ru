---
title: pInvokeStackImbalance MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 117e0838f78d43bf9ffa555947bf8749830c9840
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801993"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="15dec-102">PInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="15dec-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="15dec-103">Помощник по отладке управляемого кода (MDA) `PInvokeStackImbalance` активируется, когда среда CLR обнаруживает, что глубина стека после вызова неуправляемого кода не соответствует ожидаемой глубине стека, учитывая соглашение о вызовах, указанное в атрибуте <xref:System.Runtime.InteropServices.DllImportAttribute>, и объявление параметров в управляемой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="15dec-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="15dec-104">MDA `PInvokeStackImbalance` реализован только для 32-разрядных платформ x86.</span><span class="sxs-lookup"><span data-stu-id="15dec-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="15dec-105">По умолчанию `PInvokeStackImbalance` MDA отключен.</span><span class="sxs-lookup"><span data-stu-id="15dec-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="15dec-106">В Visual Studio 2017 и более поздних версиях `PInvokeStackImbalance` MDA отображается в списке **помощники по отладке управляемого** кода в диалоговом окне **параметры исключений** (которое отображается при выборе параметра **Отладка** > **Windows** > **параметры исключения**).</span><span class="sxs-lookup"><span data-stu-id="15dec-106">In Visual Studio 2017 and later versions, the `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="15dec-107">Однако установка или снятие флажка **прерывать при возникновении** не включает и не отключает MDA. Он только определяет, создает ли Visual Studio исключение при активации MDA.</span><span class="sxs-lookup"><span data-stu-id="15dec-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="15dec-108">Симптомы</span><span class="sxs-lookup"><span data-stu-id="15dec-108">Symptoms</span></span>

<span data-ttu-id="15dec-109">В приложении обнаружено нарушение прав доступа или повреждение памяти при выполнении или отслеживании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="15dec-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="15dec-110">Причина</span><span class="sxs-lookup"><span data-stu-id="15dec-110">Cause</span></span>

<span data-ttu-id="15dec-111">Управляемая сигнатура вызова неуправляемого кода может не соответствовать неуправляемой сигнатуре вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="15dec-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="15dec-112">Это несоответствие может быть вызвано тем, что управляемая сигнатура не объявляет правильное количество параметров или не задает соответствующий размер для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="15dec-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="15dec-113">MDA также может активироваться, поскольку соглашение о вызовах, возможно указанное атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute>, не соответствует соглашению о вызовах неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="15dec-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="15dec-114">Разрешение</span><span class="sxs-lookup"><span data-stu-id="15dec-114">Resolution</span></span>

<span data-ttu-id="15dec-115">Просмотрите сигнатуру вызова неуправляемого кода и соглашение о вызовах, чтобы убедиться, что они соответствуют сигнатуре и соглашению о вызовах исходного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="15dec-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="15dec-116">Попробуйте явным образом задать соглашение о вызовах для управляемой и неуправляемой сторон.</span><span class="sxs-lookup"><span data-stu-id="15dec-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="15dec-117">Также возможно, хотя и маловероятно, что неуправляемая функция внесла дисбаланс в стек по какой-либо другой причине, например из-за ошибки в неуправляемом компиляторе.</span><span class="sxs-lookup"><span data-stu-id="15dec-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="15dec-118">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="15dec-118">Effect on the Runtime</span></span>

<span data-ttu-id="15dec-119">Заставляет все вызовы неуправляемого кода принимать неоптимизированный путь в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="15dec-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="15dec-120">Вывод</span><span class="sxs-lookup"><span data-stu-id="15dec-120">Output</span></span>

<span data-ttu-id="15dec-121">Сообщение MDA предоставляет имя вызова метода вызова неуправляемого кода, который привел к несбалансированности стека вызова.</span><span class="sxs-lookup"><span data-stu-id="15dec-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="15dec-122">Пример сообщения вызова неуправляемого кода в методе `SampleMethod`:</span><span class="sxs-lookup"><span data-stu-id="15dec-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="15dec-123">**Вызов функции PInvoke "SampleMethod" не сбалансирован стек. Скорее всего, это связано с тем, что управляемая сигнатура PInvoke не соответствует неуправляемой сигнатуре целевого объекта. Убедитесь, что соглашение о вызовах и параметры сигнатуры PInvoke соответствуют целевой неуправляемой подписи.**</span><span class="sxs-lookup"><span data-stu-id="15dec-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="15dec-124">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="15dec-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="15dec-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="15dec-125">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="15dec-126">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="15dec-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="15dec-127">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="15dec-127">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
