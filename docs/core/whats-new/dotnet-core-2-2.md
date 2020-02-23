---
title: Новые возможности .NET Core 2.2
description: Дополнительные сведения о новых возможностях .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: 9495288658fa102df8f0fbd643e2fcdf49d8f3b3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451984"
---
# <a name="whats-new-in-net-core-22"></a><span data-ttu-id="36dc1-103">Новые возможности .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="36dc1-103">What's new in .NET Core 2.2</span></span>

<span data-ttu-id="36dc1-104">.NET Core 2.2 содержит улучшения развертывания приложений, обработки событий для служб среды выполнения, проверки подлинности в базах данных SQL Azure, производительности JIT-компилятора и внедрении кода перед выполнением метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="36dc1-104">.NET Core 2.2 includes enhancements in application deployment, event handling for runtime services, authentication to Azure SQL databases, JIT compiler performance, and code injection prior to the execution of the `Main` method.</span></span>

## <a name="new-deployment-mode"></a><span data-ttu-id="36dc1-105">Новый режим развертывания</span><span class="sxs-lookup"><span data-stu-id="36dc1-105">New deployment mode</span></span>

<span data-ttu-id="36dc1-106">Начиная с .NET Core 2.2, вы можете развертывать [зависящие от платформы исполняемые файлы](../deploying/index.md#publish-runtime-dependent) **.exe** вместо файлов **.dll**.</span><span class="sxs-lookup"><span data-stu-id="36dc1-106">Starting with .NET Core 2.2, you can deploy [framework-dependent executables](../deploying/index.md#publish-runtime-dependent), which are **.exe** files instead of **.dll** files.</span></span> <span data-ttu-id="36dc1-107">Функционально похожие на зависящие от платформы развертывания, зависящие от платформы исполняемые файлы (FDE) для запуска по-прежнему требуют наличия общедоступной на уровне системы версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36dc1-107">Functionally similar to framework-dependent deployments, framework-dependent executables (FDE) still rely on the presence of a shared system-wide version of .NET Core to run.</span></span> <span data-ttu-id="36dc1-108">Ваше приложение содержит только ваш код и зависимости сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="36dc1-108">Your app contains only your code and any third-party dependencies.</span></span> <span data-ttu-id="36dc1-109">В отличие от развертываний, зависящих от платформ, FDE зависят от конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="36dc1-109">Unlike framework-dependent deployments, FDEs are platform-specific.</span></span>

<span data-ttu-id="36dc1-110">Этот новый режим развертывания обладает явным преимуществом создания исполняемого файла вместо библиотеки, что позволяет вам запускать приложение напрямую без вызова `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="36dc1-110">This new deployment mode has the distinct advantage of building an executable instead of a library, which means you can run your app directly without invoking `dotnet` first.</span></span>

## <a name="core"></a><span data-ttu-id="36dc1-111">Ядро</span><span class="sxs-lookup"><span data-stu-id="36dc1-111">Core</span></span>

<span data-ttu-id="36dc1-112">**Обработка событий в службах среды выполнения**</span><span class="sxs-lookup"><span data-stu-id="36dc1-112">**Handling events in runtime services**</span></span>

<span data-ttu-id="36dc1-113">Часто может возникать необходимость в отслеживании использования приложением служб среды выполнения, таких как GC, JIT и ThreadPool, чтобы понять, как они влияют на ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="36dc1-113">You may often want to monitor your application's use of runtime services, such as the GC, JIT, and ThreadPool, to understand how they impact your application.</span></span><span data-ttu-id="36dc1-114"> В системах Windows это обычно выполняется путем мониторинга событий ETW текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="36dc1-114"> On Windows systems, this is commonly done by monitoring the ETW events of the current process.</span></span><span data-ttu-id="36dc1-115"> Несмотря на то что такой подход эффективен, использование ETW возможно не всегда, особенно если вы работаете в среде с низким уровнем привилегий либо в Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="36dc1-115"> While this continues to work well, it's not always possible to use ETW if you're running in a low-privilege environment or on Linux or macOS.</span></span> 

<span data-ttu-id="36dc1-116">Начиная с .NET Core 2.2, события CoreCLR теперь можно использовать с помощью класса <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36dc1-116">Starting with .NET Core 2.2, CoreCLR events can now be consumed using the <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="36dc1-117">Эти события описывают поведение таких служб среды выполнения, как GC, JIT, ThreadPool и Interop.</span><span class="sxs-lookup"><span data-stu-id="36dc1-117">These events describe the behavior of such runtime services as GC, JIT, ThreadPool, and interop.</span></span> <span data-ttu-id="36dc1-118">Эти же события являются частью поставщика трассировки событий Windows в CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="36dc1-118">These are the same events that are exposed as part of the CoreCLR ETW provider.</span></span><span data-ttu-id="36dc1-119">  Это позволяет приложениям использовать данные события или механизм транспортировки для отправки их в службу агрегирования телеметрии.</span><span class="sxs-lookup"><span data-stu-id="36dc1-119">  This allows for applications to consume these events or use a transport mechanism to send them to a telemetry aggregation service.</span></span> <span data-ttu-id="36dc1-120">В приведенном ниже примере кода показано, как можно подписаться на события:</span><span class="sxs-lookup"><span data-stu-id="36dc1-120">You can see how to subscribe to events in the following code sample:</span></span>

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

<span data-ttu-id="36dc1-121">Кроме того, .NET Core 2.2 добавляет следующие два свойства в класс <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> для предоставления дополнительных сведений о событиях ETW:</span><span class="sxs-lookup"><span data-stu-id="36dc1-121">In addition, .NET Core 2.2 adds the following two properties to the <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> class to provide additional information about ETW events:</span></span>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a><span data-ttu-id="36dc1-122">Данные</span><span class="sxs-lookup"><span data-stu-id="36dc1-122">Data</span></span>

<span data-ttu-id="36dc1-123">**Проверка подлинности Azure Active Directory в базах данных SQL Azure с помощью свойства SqlConnection.AccessToken**</span><span class="sxs-lookup"><span data-stu-id="36dc1-123">**AAD authentication to Azure SQL databases with the SqlConnection.AccessToken property**</span></span>

<span data-ttu-id="36dc1-124">Начиная с .NET Core 2.2, маркер доступа, выданный Azure Active Directory, можно использовать для проверки подлинности в базе данных SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="36dc1-124">Starting with .NET Core 2.2, an access token issued by Azure Active Directory can be used to authenticate to an Azure SQL database.</span></span> <span data-ttu-id="36dc1-125">Для поддержки маркеров доступа в класс <xref:System.Data.SqlClient.SqlConnection> было добавлено свойство <xref:System.Data.SqlClient.SqlConnection.AccessToken>.</span><span class="sxs-lookup"><span data-stu-id="36dc1-125">To support access tokens, the <xref:System.Data.SqlClient.SqlConnection.AccessToken> property has been added to the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="36dc1-126">Чтобы воспользоваться преимуществами проверки подлинности Azure Active Directory, скачайте версию 4.6 пакета NuGet System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="36dc1-126">To take advantage of AAD authentication, download version 4.6 of the System.Data.SqlClient NuGet package.</span></span> <span data-ttu-id="36dc1-127">Для использования этой функции вы можете получить значение маркера доступа с помощью [Библиотеки проверки подлинности Active Directory для .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet), содержащейся в пакете NuGet [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="36dc1-127">In order to use the feature, you can obtain the access token value using the [Active Directory Authentication Library for .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contained in the [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet package.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="36dc1-128">Усовершенствования JIT-компилятора</span><span class="sxs-lookup"><span data-stu-id="36dc1-128">JIT compiler improvements</span></span>

<span data-ttu-id="36dc1-129">**Функцию многоуровневой компиляции все еще должен включать пользователь**</span><span class="sxs-lookup"><span data-stu-id="36dc1-129">**Tiered compilation remains an opt-in feature**</span></span>

<span data-ttu-id="36dc1-130">В .NET Core 2.1 JIT-компилятор реализовал в качестве дополнительной функции новую технологию компилятора — *многоуровневую компиляцию*.</span><span class="sxs-lookup"><span data-stu-id="36dc1-130">In .NET Core 2.1, the JIT compiler implemented a new compiler technology, *tiered compilation*, as an opt-in feature.</span></span> <span data-ttu-id="36dc1-131">Целью многоуровневой компиляции является повышение уровня производительности.</span><span class="sxs-lookup"><span data-stu-id="36dc1-131">The goal of tiered compilation is improved performance.</span></span> <span data-ttu-id="36dc1-132">Одна из важных задач, которую выполняет JIT-компилятор, это оптимизация выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="36dc1-132">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="36dc1-133">Но для редко используемых путей кода компилятор может потратить на оптимизацию больше времени, чем потребуется на выполнение неоптимизированного кода.</span><span class="sxs-lookup"><span data-stu-id="36dc1-133">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends executing unoptimized code.</span></span> <span data-ttu-id="36dc1-134">Многоуровневая компиляция разделяет JIT-компиляцию на два уровня.</span><span class="sxs-lookup"><span data-stu-id="36dc1-134">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="36dc1-135">**Первый уровень** создает код настолько быстро, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="36dc1-135">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="36dc1-136">**Второй уровень** создает оптимизированный код для тех методов, которые выполняются часто.</span><span class="sxs-lookup"><span data-stu-id="36dc1-136">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="36dc1-137">Второй уровень компиляции выполняется параллельно, чтобы повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="36dc1-137">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="36dc1-138">Сведения об улучшении производительности, которое может быть результатом многоуровневой компиляции, см. в записи блога об [объявлении .NET Core 2.2 (предварительная версия 2)](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="36dc1-138">For information on the performance improvement that can result from tiered compilation, see [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span>

<span data-ttu-id="36dc1-139">В предварительной версии 2 .NET Core 2.2 многоуровневая компиляция была включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36dc1-139">In .NET Core 2.2 Preview 2, tiered compilation was enabled by default.</span></span> <span data-ttu-id="36dc1-140">Однако мы решили, что все еще не готовы включить эту функцию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36dc1-140">However, we've decided that we are still not ready to enable tiered compilation by default.</span></span> <span data-ttu-id="36dc1-141">Таким образом, в .NET Core 2.2 многоуровневую компиляцию должен включать пользователь.</span><span class="sxs-lookup"><span data-stu-id="36dc1-141">So in .NET Core 2.2, tiered compilation continues to be an opt-in feature.</span></span> <span data-ttu-id="36dc1-142">Сведения о включении многоуровневой компиляции см. в разделе [Усовершенствования JIT-компилятора](dotnet-core-2-1.md#jit-compiler-improvements) в статье [Новые возможности .NET Core 2.1](dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="36dc1-142">For information on opting in to tiered compilation, see [Jit compiler improvements](dotnet-core-2-1.md#jit-compiler-improvements) in [What's new in .NET Core 2.1](dotnet-core-2-1.md).</span></span>

## <a name="runtime"></a><span data-ttu-id="36dc1-143">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="36dc1-143">Runtime</span></span>

<span data-ttu-id="36dc1-144">**Внедрение кода перед выполнением метода Main**</span><span class="sxs-lookup"><span data-stu-id="36dc1-144">**Injecting code prior to executing the Main method**</span></span>

<span data-ttu-id="36dc1-145">Начиная с .NET Core 2.2, вы можете использовать перехватчик запуска для внедрения кода перед запуском метода Main в приложении.</span><span class="sxs-lookup"><span data-stu-id="36dc1-145">Starting with .NET Core 2.2, you can use a startup hook to inject code prior to running an application's Main method.</span></span> <span data-ttu-id="36dc1-146">Перехватчики запуска позволяют узлу настраивать поведение приложений после их развертывания без необходимости выполнения повторной компиляции или изменения приложения.</span><span class="sxs-lookup"><span data-stu-id="36dc1-146">Startup hooks make it possible for a host to customize the behavior of applications after they have been deployed without needing to recompile or change the application.</span></span>

<span data-ttu-id="36dc1-147">Мы ожидаем, что поставщики услуг размещения определят пользовательскую конфигурацию и политику, включая параметры, которые потенциально могут влиять на поведение загрузки основной точки входа, например поведение <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36dc1-147">We expect hosting providers to define custom configuration and policy, including settings that potentially influence the load behavior of the main entry point, such as the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> behavior.</span></span> <span data-ttu-id="36dc1-148">С помощью перехватчика можно настраивать трассировку или внедрять данные телеметрии, а также настраивать обратные вызовы для обработки или определять другое поведение, зависящее от среды.</span><span class="sxs-lookup"><span data-stu-id="36dc1-148">The hook can be used to set up tracing or telemetry injection, to set up callbacks for handling, or to define other environment-dependent behavior.</span></span> <span data-ttu-id="36dc1-149">Перехватчик отделен от точки входа, поэтому нет необходимости изменять код пользователя.</span><span class="sxs-lookup"><span data-stu-id="36dc1-149">The hook is separate from the entry point, so that user code doesn't need to be modified.</span></span>

<span data-ttu-id="36dc1-150">Дополнительные сведения см. в статье о [размещении перехватчиков запуска](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md).</span><span class="sxs-lookup"><span data-stu-id="36dc1-150">See [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="36dc1-151">См. также</span><span class="sxs-lookup"><span data-stu-id="36dc1-151">See also</span></span>

- [<span data-ttu-id="36dc1-152">Новые возможности .NET Core</span><span class="sxs-lookup"><span data-stu-id="36dc1-152">What's new in .NET Core</span></span>](index.md)
- [<span data-ttu-id="36dc1-153">Новые возможности ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="36dc1-153">What's new in ASP.NET Core 2.2</span></span>](/aspnet/core/release-notes/aspnetcore-2.2)
- [<span data-ttu-id="36dc1-154">Новые возможности в EF Core 2.2</span><span class="sxs-lookup"><span data-stu-id="36dc1-154">New features in EF Core 2.2</span></span>](/ef/core/what-is-new/ef-core-2.2)
