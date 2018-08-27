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
ms.openlocfilehash: 5594166081c36fbda1e5d1a62e017aaceb7a553d
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912118"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="30a51-102">PInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="30a51-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="30a51-103">`PInvokeStackImbalance` Помощник по отладке управляемого (кода MDA) активируется в том случае, когда среда CLR обнаруживает, что глубина стека после вызова неуправляемого кода не соответствует ожидаемой глубине стека, учитывая соглашение о вызовах, указанное в <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут и Объявление параметров в управляемой подписи.</span><span class="sxs-lookup"><span data-stu-id="30a51-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="30a51-104">MDA `PInvokeStackImbalance` реализован только для 32-разрядных платформ x86.</span><span class="sxs-lookup"><span data-stu-id="30a51-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="30a51-105">`PInvokeStackImbalance` MDA отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="30a51-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="30a51-106">В Visual Studio 2017 `PInvokeStackImbalance` MDA отображается в **Помощники отладки управляемого кода** в списке **параметры исключений** диалоговое окно (которое отображается при выборе **Отладка**  >  **Windows** > **параметры исключений**).</span><span class="sxs-lookup"><span data-stu-id="30a51-106">In Visual Studio 2017, The `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="30a51-107">Тем не менее, установив или сняв **прервать при исключение** "флажок" включить или отключить MDA; управляет только тем, вызывает ли Visual Studio исключение, когда MDA активирован.</span><span class="sxs-lookup"><span data-stu-id="30a51-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="30a51-108">Симптомы</span><span class="sxs-lookup"><span data-stu-id="30a51-108">Symptoms</span></span>

<span data-ttu-id="30a51-109">В приложении обнаружено нарушение прав доступа или повреждение памяти при выполнении или отслеживании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="30a51-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="30a51-110">Причина</span><span class="sxs-lookup"><span data-stu-id="30a51-110">Cause</span></span>

<span data-ttu-id="30a51-111">Управляемая сигнатура вызова неуправляемого кода может не соответствовать неуправляемой сигнатуре вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="30a51-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="30a51-112">Это несоответствие может быть вызвано тем, что управляемая сигнатура не объявляет правильное количество параметров или не задает соответствующий размер для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="30a51-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="30a51-113">MDA также может активироваться, поскольку соглашение о вызовах, возможно указанное атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute>, не соответствует соглашению о вызовах неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="30a51-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="30a51-114">Решение</span><span class="sxs-lookup"><span data-stu-id="30a51-114">Resolution</span></span>

<span data-ttu-id="30a51-115">Просмотрите сигнатуру вызова неуправляемого кода и соглашение о вызовах, чтобы убедиться, что они соответствуют сигнатуре и соглашению о вызовах исходного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="30a51-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="30a51-116">Попробуйте явным образом задать соглашение о вызовах для управляемой и неуправляемой сторон.</span><span class="sxs-lookup"><span data-stu-id="30a51-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="30a51-117">Также возможно, хотя и маловероятно, что неуправляемая функция внесла дисбаланс в стек по какой-либо другой причине, например из-за ошибки в неуправляемом компиляторе.</span><span class="sxs-lookup"><span data-stu-id="30a51-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="30a51-118">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="30a51-118">Effect on the Runtime</span></span>

<span data-ttu-id="30a51-119">Заставляет все вызовы неуправляемого кода принимать неоптимизированный путь в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="30a51-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="30a51-120">Вывод</span><span class="sxs-lookup"><span data-stu-id="30a51-120">Output</span></span>

<span data-ttu-id="30a51-121">Сообщение MDA предоставляет имя вызова метода вызова неуправляемого кода, который привел к несбалансированности стека вызова.</span><span class="sxs-lookup"><span data-stu-id="30a51-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="30a51-122">Пример сообщения вызова неуправляемого кода в методе `SampleMethod`:</span><span class="sxs-lookup"><span data-stu-id="30a51-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="30a51-123">**Вызов функции PInvoke «SampleMethod» внесла дисбаланс в стек. Это обусловлено тем, скорее всего, управляемая сигнатура PInvoke не соответствует сигнатуре неуправляемого целевой. Проверьте, что соглашение о вызовах и параметры подписи PInvoke соответствовать неуправляемой сигнатуре целевой объект.**</span><span class="sxs-lookup"><span data-stu-id="30a51-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="30a51-124">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="30a51-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="30a51-125">См. также</span><span class="sxs-lookup"><span data-stu-id="30a51-125">See Also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="30a51-126">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="30a51-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="30a51-127">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="30a51-127">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
