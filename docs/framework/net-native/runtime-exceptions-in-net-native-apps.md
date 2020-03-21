---
title: Исключения среды выполнения в собственных приложениях .NET
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
ms.openlocfilehash: 12df2ef7bf6e86a60dfa4c130f35969e72ac5211
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180949"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="3d1c5-102">Исключения среды выполнения в собственных приложениях .NET</span><span class="sxs-lookup"><span data-stu-id="3d1c5-102">Runtime Exceptions in .NET Native Apps</span></span>
<span data-ttu-id="3d1c5-103">Очень важно выполнять тестирование сборок выпуска приложения универсальной платформы Windows на их целевых платформах, поскольку конфигурации отладки и выпуска совершенно различны.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="3d1c5-104">По умолчанию конфигурация отладки использует для компиляции приложения среду выполнения .NET Core, но конфигурация выпуска использует для компиляции приложения в машинный код среду выполнения .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3d1c5-105">Для получения информации о работе с [MissingMetadataException](missingmetadataexception-class-net-native.md) [Getting Started](getting-started-with-net-native.md) , [MissingInteropDataException](missinginteropdataexception-class-net-native.md), и [MissingRuntimeArtifact Исключения](missingruntimeartifactexception-class-net-native.md) исключения, которые вы можете столкнуться при тестировании версии релиза [Reflection and .NET Native](reflection-and-net-native.md) вашего приложения, [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md)см.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-105">For information on dealing with the [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see "Step 4: Manually resolve missing metadata: in the [Getting Started](getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="3d1c5-106">Отладочные и выпускные сборки</span><span class="sxs-lookup"><span data-stu-id="3d1c5-106">Debug and release builds</span></span>  
 <span data-ttu-id="3d1c5-107">Когда отладочная сборка выполняется в среде выполнения .NET Core, она не компилируется в машинный код.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="3d1c5-108">Это делает все службы, обычно предоставляемые средой выполнения, доступными вашему приложению.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="3d1c5-109">С другой стороны, выпускная сборка компилируется в машинный код для целевых платформ, при этом удаляется большинство зависимостей от внешних сред выполнения и библиотек и выполняется серьезная оптимизация кода для достижения максимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="3d1c5-110">При отладке выпускных сборок, которые компилируются с помощью .NET Native, происходит следующее.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
- <span data-ttu-id="3d1c5-111">Вы используете модуль отладки .NET Native, который отличается от обычных средств отладки .NET.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
- <span data-ttu-id="3d1c5-112">Размер исполняемого файла максимально уменьшается.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="3d1c5-113">Один из способов, которым .NET Native уменьшает размер исполняемого файла, состоит в значительном сокращении сообщений об исключениях времени выполнения. Это более подробно рассматривается в разделе [Runtime exception messages](#Messages) .</span><span class="sxs-lookup"><span data-stu-id="3d1c5-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
- <span data-ttu-id="3d1c5-114">Код сильно оптимизируется.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-114">Your code is heavily optimized.</span></span> <span data-ttu-id="3d1c5-115">Это означает, что везде, где это возможно, используется встраивание.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="3d1c5-116">(Inlining перемещает код из внешних процедур в процедуру вызова.)   Тот факт, что .NET Native предоставляет специализированное время выполнения и реализует агрессивную подстилку, влияет на стек вызовов, который отображается при отладке.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="3d1c5-117">Дополнительные сведения см. в разделе [Runtime call stack](#CallStack) .</span><span class="sxs-lookup"><span data-stu-id="3d1c5-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d1c5-118">Вы можете управлять тем, будут ли отладочные и выпускные сборки компилироваться с помощью цепочки инструментов .NET Native, устанавливая или снимая флажок **Компилировать с использованием цепочки инструментов машинного кода .NET** .</span><span class="sxs-lookup"><span data-stu-id="3d1c5-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="3d1c5-119">Однако обратите внимание, что Магазин Windows всегда будет компилировать рабочую версию вашего приложения с помощью цепочки инструментов .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>
## <a name="runtime-exception-messages"></a><span data-ttu-id="3d1c5-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="3d1c5-120">Runtime exception messages</span></span>  
 <span data-ttu-id="3d1c5-121">Чтобы свести к минимуму размер исполняемого файла приложения, .NET Native не включает полный текст сообщений об исключениях.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="3d1c5-122">В результате исключения среды выполнения, возникающие в выпускной сборке, могут не отображать полный текст сообщений об исключениях.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="3d1c5-123">Вместо этого текст может содержать подстроку со ссылкой на дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="3d1c5-124">Например, сведения об исключении могут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d1c5-124">For example, the exception information may appear as:</span></span>  
  
```output
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="3d1c5-125">Если вам требуется полное сообщение об исключении, запустите отладочную сборку.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="3d1c5-126">Например, предыдущие сведения об исключении из выпускной сборки могут выглядеть в отладочной сборке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d1c5-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```output
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>
## <a name="runtime-call-stack"></a><span data-ttu-id="3d1c5-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="3d1c5-127">Runtime call stack</span></span>  
 <span data-ttu-id="3d1c5-128">Из-за встраивания и других видов оптимизации стек вызовов, отображаемый приложением, которое скомпилировано цепочкой инструментов .NET Native, может не позволить вам четко определить путь к исключению среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="3d1c5-129">Чтобы получить полный стек, запустите отладочную сборку.</span><span class="sxs-lookup"><span data-stu-id="3d1c5-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1c5-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d1c5-130">See also</span></span>

- [<span data-ttu-id="3d1c5-131">Отладка универсальных приложений Windows .NET в .NET Native</span><span class="sxs-lookup"><span data-stu-id="3d1c5-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="3d1c5-132">Начало работы</span><span class="sxs-lookup"><span data-stu-id="3d1c5-132">Getting Started</span></span>](getting-started-with-net-native.md)
