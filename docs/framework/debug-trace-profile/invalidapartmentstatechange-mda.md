---
title: Помощник по отладке управляемого кода invalidApartmentStateChange
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
ms.openlocfilehash: 8acafcc2fba9a7d30cc77f25f06adaca7c79db32
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217416"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="963af-102">Помощник по отладке управляемого кода invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="963af-102">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="963af-103">Помощник по отладке управляемого кода (MDA) `invalidApartmentStateChange` активируется при возникновении одной из двух следующих проблем.</span><span class="sxs-lookup"><span data-stu-id="963af-103">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
- <span data-ttu-id="963af-104">Предпринята попытка изменить состояние подразделения COM потока, который уже был инициализирован COM в другом состоянии подразделения.</span><span class="sxs-lookup"><span data-stu-id="963af-104">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
- <span data-ttu-id="963af-105">Неожиданное изменение состояния подразделения COM потока.</span><span class="sxs-lookup"><span data-stu-id="963af-105">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="963af-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="963af-106">Symptoms</span></span>  
  
- <span data-ttu-id="963af-107">Состояние подразделения COM отличается от запрошенного.</span><span class="sxs-lookup"><span data-stu-id="963af-107">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="963af-108">Это может привести к использованию прокси-серверов для COM-компонентов, имеющих потоковую модель, отличную от текущей.</span><span class="sxs-lookup"><span data-stu-id="963af-108">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="963af-109">Это, в свою очередь, может привести к возникновению исключения <xref:System.InvalidCastException> при вызове COM-объекта через интерфейсы, которые не настроены для маршалинга между подразделениями.</span><span class="sxs-lookup"><span data-stu-id="963af-109">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
- <span data-ttu-id="963af-110">Состояние подразделения COM потока отличается от ожидаемого.</span><span class="sxs-lookup"><span data-stu-id="963af-110">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="963af-111">Это может привести к <xref:System.Runtime.InteropServices.COMException> с HRESULT RPC_E_WRONG_THREAD, а также <xref:System.InvalidCastException> при вызовах [вызываемой оболочки времени выполнения](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="963af-111">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="963af-112">Кроме того, сразу несколько потоков могут одновременно осуществлять доступ к некоторым однопоточным COM-компонентам, что может привести к повреждению или потере данных.</span><span class="sxs-lookup"><span data-stu-id="963af-112">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="963af-113">Причина</span><span class="sxs-lookup"><span data-stu-id="963af-113">Cause</span></span>  
  
- <span data-ttu-id="963af-114">Поток ранее был инициализирован в другом состоянии подразделения СОМ.</span><span class="sxs-lookup"><span data-stu-id="963af-114">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="963af-115">Обратите внимание, что состояние потока подразделения может быть задано явным или неявным образом.</span><span class="sxs-lookup"><span data-stu-id="963af-115">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="963af-116">Явные операции содержат свойство <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> и методы <xref:System.Threading.Thread.SetApartmentState%2A> и <xref:System.Threading.Thread.TrySetApartmentState%2A>.</span><span class="sxs-lookup"><span data-stu-id="963af-116">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="963af-117">Поток, созданный с помощью метода <xref:System.Threading.Thread.Start%2A>, неявно задан как <xref:System.Threading.ApartmentState.MTA> до тех пор, пока <xref:System.Threading.Thread.SetApartmentState%2A> не будет вызван до запуска потока.</span><span class="sxs-lookup"><span data-stu-id="963af-117">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="963af-118">Основной поток приложения также неявно инициализирован как <xref:System.Threading.ApartmentState.MTA> до тех пор, пока в основном методе не будет указан атрибут <xref:System.STAThreadAttribute>.</span><span class="sxs-lookup"><span data-stu-id="963af-118">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
- <span data-ttu-id="963af-119">В потоке вызван метод `CoUninitialize` (или метод `CoInitializeEx`) с другой моделью параллелизма.</span><span class="sxs-lookup"><span data-stu-id="963af-119">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="963af-120">Решение</span><span class="sxs-lookup"><span data-stu-id="963af-120">Resolution</span></span>  
 <span data-ttu-id="963af-121">Задайте состояние подразделения потока перед началом его выполнения либо примените атрибут <xref:System.STAThreadAttribute> или <xref:System.MTAThreadAttribute> атрибут к основному методу приложения.</span><span class="sxs-lookup"><span data-stu-id="963af-121">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="963af-122">Во втором случае в идеале код, вызывающий метод `CoUninitialize`, следует изменить для задержки вызова до тех пор, пока поток не будет завершен и не перестанет использовать RCW и базовые СОМ-компоненты.</span><span class="sxs-lookup"><span data-stu-id="963af-122">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="963af-123">Однако если не удается изменить код, который вызывает метод`CoUninitialize`, то нельзя использовать RCW из потоков, для которых выполнена отмена инициализации.</span><span class="sxs-lookup"><span data-stu-id="963af-123">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="963af-124">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="963af-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="963af-125">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="963af-125">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="963af-126">Вывод</span><span class="sxs-lookup"><span data-stu-id="963af-126">Output</span></span>  
 <span data-ttu-id="963af-127">Состояние контейнера СОМ текущего потока и состояние, которое пытался применить код.</span><span class="sxs-lookup"><span data-stu-id="963af-127">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="963af-128">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="963af-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="963af-129">Пример</span><span class="sxs-lookup"><span data-stu-id="963af-129">Example</span></span>  
 <span data-ttu-id="963af-130">Следующий пример кода демонстрирует ситуацию, которая может активировать данный MDA.</span><span class="sxs-lookup"><span data-stu-id="963af-130">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="963af-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="963af-131">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="963af-132">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="963af-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="963af-133">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="963af-133">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
