---
title: Новые возможности .NET Core 2.2
description: Дополнительные сведения о новых возможностях .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: e045c39240c99777d05ca86ee0a8cd1fa4309c4f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156586"
---
# <a name="whats-new-in-net-core-22"></a>Новые возможности .NET Core 2.2

.NET Core 2.2 содержит улучшения развертывания приложений, обработки событий для служб среды выполнения, проверки подлинности в базах данных SQL Azure, производительности JIT-компилятора и внедрении кода перед выполнением метода `Main`.

## <a name="new-deployment-mode"></a>Новый режим развертывания

Начиная с .NET Core 2.2, вы можете развертывать [зависящие от платформы исполняемые файлы](../deploying/index.md#publish-runtime-dependent) **.exe** вместо файлов **.dll**. Функционально похожие на зависящие от платформы развертывания, зависящие от платформы исполняемые файлы (FDE) для запуска по-прежнему требуют наличия общедоступной на уровне системы версии .NET Core. Ваше приложение содержит только ваш код и зависимости сторонних разработчиков. В отличие от развертываний, зависящих от платформ, FDE зависят от конкретной платформы.

Этот новый режим развертывания обладает явным преимуществом создания исполняемого файла вместо библиотеки, что позволяет вам запускать приложение напрямую без вызова `dotnet`.

## <a name="core"></a>Ядро

**Обработка событий в службах среды выполнения**

Часто может возникать необходимость в отслеживании использования приложением служб среды выполнения, таких как GC, JIT и ThreadPool, чтобы понять, как они влияют на ваше приложение. В системах Windows это обычно выполняется путем мониторинга событий ETW текущего процесса. Несмотря на то что такой подход эффективен, использование ETW возможно не всегда, особенно если вы работаете в среде с низким уровнем привилегий либо в Linux или macOS.

Начиная с .NET Core 2.2, события CoreCLR теперь можно использовать с помощью класса <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>. Эти события описывают поведение таких служб среды выполнения, как GC, JIT, ThreadPool и Interop. Эти же события являются частью поставщика трассировки событий Windows в CoreCLR.  Это позволяет приложениям использовать данные события или механизм транспортировки для отправки их в службу агрегирования телеметрии. В приведенном ниже примере кода показано, как можно подписаться на события:

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

Кроме того, .NET Core 2.2 добавляет следующие два свойства в класс <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> для предоставления дополнительных сведений о событиях ETW:

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a>Данные

**Проверка подлинности Azure Active Directory в базах данных SQL Azure с помощью свойства SqlConnection.AccessToken**

Начиная с .NET Core 2.2, маркер доступа, выданный Azure Active Directory, можно использовать для проверки подлинности в базе данных SQL Azure. Для поддержки маркеров доступа в класс <xref:System.Data.SqlClient.SqlConnection> было добавлено свойство <xref:System.Data.SqlClient.SqlConnection.AccessToken>. Чтобы воспользоваться преимуществами проверки подлинности Azure Active Directory, скачайте версию 4.6 пакета NuGet System.Data.SqlClient. Для использования этой функции вы можете получить значение маркера доступа с помощью [Библиотеки проверки подлинности Active Directory для .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet), содержащейся в пакете NuGet [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

## <a name="jit-compiler-improvements"></a>Усовершенствования JIT-компилятора

**Функцию многоуровневой компиляции все еще должен включать пользователь**

В .NET Core 2.1 JIT-компилятор реализовал в качестве дополнительной функции новую технологию компилятора — *многоуровневую компиляцию*. Целью многоуровневой компиляции является повышение уровня производительности. Одна из важных задач, которую выполняет JIT-компилятор, это оптимизация выполнения кода. Но для редко используемых путей кода компилятор может потратить на оптимизацию больше времени, чем потребуется на выполнение неоптимизированного кода. Многоуровневая компиляция разделяет JIT-компиляцию на два уровня.

- **Первый уровень** создает код настолько быстро, насколько это возможно.

- **Второй уровень** создает оптимизированный код для тех методов, которые выполняются часто. Второй уровень компиляции выполняется параллельно, чтобы повысить производительность.

Сведения об улучшении производительности, которое может быть результатом многоуровневой компиляции, см. в записи блога об [объявлении .NET Core 2.2 (предварительная версия 2)](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).

В предварительной версии 2 .NET Core 2.2 многоуровневая компиляция была включена по умолчанию. Однако мы решили, что все еще не готовы включить эту функцию по умолчанию. Таким образом, в .NET Core 2.2 многоуровневую компиляцию должен включать пользователь. Сведения о включении многоуровневой компиляции см. в разделе [Усовершенствования JIT-компилятора](dotnet-core-2-1.md#jit-compiler-improvements) в статье [Новые возможности .NET Core 2.1](dotnet-core-2-1.md).

## <a name="runtime"></a>Среда выполнения

**Внедрение кода перед выполнением метода Main**

Начиная с .NET Core 2.2, вы можете использовать перехватчик запуска для внедрения кода перед запуском метода Main в приложении. Перехватчики запуска позволяют узлу настраивать поведение приложений после их развертывания без необходимости выполнения повторной компиляции или изменения приложения.

Мы ожидаем, что поставщики услуг размещения определят пользовательскую конфигурацию и политику, включая параметры, которые потенциально могут влиять на поведение загрузки основной точки входа, например поведение <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> . С помощью перехватчика можно настраивать трассировку или внедрять данные телеметрии, а также настраивать обратные вызовы для обработки или определять другое поведение, зависящее от среды. Перехватчик отделен от точки входа, поэтому нет необходимости изменять код пользователя.

Дополнительные сведения см. в статье о [размещении перехватчиков запуска](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md).

## <a name="see-also"></a>См. также

- [Новые возможности .NET Core](index.md)
- [Новые возможности ASP.NET Core 2.2](/aspnet/core/release-notes/aspnetcore-2.2)
- [Новые возможности в EF Core 2.2](/ef/core/what-is-new/ef-core-2.2)
