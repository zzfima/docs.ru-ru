---
title: Практическое руководство. Создание и инициализация прослушивателей трассировки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea5db2ba1060479f55bbd7f67266d36085a2535f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754379"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="8a955-102">Практическое руководство. Создание и инициализация прослушивателей трассировки</span><span class="sxs-lookup"><span data-stu-id="8a955-102">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="8a955-103">Классы <xref:System.Diagnostics.Debug?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace?displayProperty=nameWithType> отправляют сообщения объектам, которые называются прослушивателями. Эти объекты получают и обрабатывают эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="8a955-103">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="8a955-104">Один из таких прослушивателей, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, автоматически создается и инициализируется при включении трассировки или отладки.</span><span class="sxs-lookup"><span data-stu-id="8a955-104">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="8a955-105">Если требуется направить выходные данные типа <xref:System.Diagnostics.Trace> или <xref:System.Diagnostics.Debug> каким-либо дополнительным источникам, необходимо создать и инициализировать дополнительные прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="8a955-105">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="8a955-106">Создаваемые прослушиватели должны соответствовать индивидуальным требованиям приложения.</span><span class="sxs-lookup"><span data-stu-id="8a955-106">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="8a955-107">Например, если требуется текстовая запись всех выходных данных трассировки, создайте прослушиватель <xref:System.Diagnostics.TextWriterTraceListener>, который будет записывать все выходные данные в новый текстовый файл, если эта функция включена.</span><span class="sxs-lookup"><span data-stu-id="8a955-107">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="8a955-108">С другой стороны, если требуется просмотреть выходные данные только во время исполнения приложения, создайте прослушиватель <xref:System.Diagnostics.ConsoleTraceListener>, направляющий все выходные данные в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="8a955-108">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="8a955-109">Прослушиватель <xref:System.Diagnostics.EventLogTraceListener> может направлять выходные данные трассировки в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="8a955-109">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="8a955-110">Дополнительные сведения см. в разделе [Прослушиватели трассировки](../../../docs/framework/debug-trace-profile/trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="8a955-110">For more information, see [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md).</span></span>

<span data-ttu-id="8a955-111">Можно создать прослушиватели трассировки в [файле конфигурации приложения](../../../docs/framework/configure-apps/index.md) или в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="8a955-111">You can create trace listeners in an [application configuration file](../../../docs/framework/configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="8a955-112">Рекомендуется использовать файлы конфигурации приложения, так как они позволяют добавлять, изменять или удалять прослушиватели трассировки без внесения изменений в код.</span><span class="sxs-lookup"><span data-stu-id="8a955-112">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="8a955-113">Создание и использование прослушивателя трассировки с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8a955-113">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="8a955-114">Объявите прослушиватель трассировки в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="8a955-114">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="8a955-115">Если создаваемый прослушиватель требует какие-либо другие объекты, также объявите их.</span><span class="sxs-lookup"><span data-stu-id="8a955-115">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="8a955-116">В следующем примере показано создание прослушивателя с именем `myListener`, записывающего данные в текстовый файл `TextWriterOutput.log`.</span><span class="sxs-lookup"><span data-stu-id="8a955-116">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

    ```xml
    <configuration>
      <system.diagnostics>
        <trace autoflush="false" indentsize="4">
          <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />
            <remove name="Default" />
          </listeners>
        </trace>
      </system.diagnostics>
    </configuration>
    ```

2. <span data-ttu-id="8a955-117">Используйте класс <xref:System.Diagnostics.Trace> в своем коде для записи сообщения в прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="8a955-117">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

    ```vb
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="8a955-118">Создание и использование прослушивателя трассировки в коде</span><span class="sxs-lookup"><span data-stu-id="8a955-118">To create and use a trace listener in code</span></span>

- <span data-ttu-id="8a955-119">Добавьте прослушиватель трассировки в коллекцию <xref:System.Diagnostics.Trace.Listeners%2A> и отправьте сведения трассировки прослушивателям.</span><span class="sxs-lookup"><span data-stu-id="8a955-119">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

    ```vb
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

    <span data-ttu-id="8a955-120">\- или -</span><span class="sxs-lookup"><span data-stu-id="8a955-120">\- or -</span></span>

- <span data-ttu-id="8a955-121">Если не нужно, чтобы прослушиватель получал выходные данные трассировки, не добавляйте его в коллекцию <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a955-121">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="8a955-122">Допускается выдача выходных данных через прослушиватель независимо от коллекции <xref:System.Diagnostics.Trace.Listeners%2A> путем вызова собственных методов вывода прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="8a955-122">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="8a955-123">В следующем примере показано, как выполнить запись строки в прослушиватель, не являющийся частью коллекции <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a955-123">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

    ```vb
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")
    myListener.WriteLine("Test message.")
    ' You must close or flush the trace listener to empty the output buffer.
    myListener.Flush()
    ```

    ```csharp
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");
    myListener.WriteLine("Test message.");
    // You must close or flush the trace listener to empty the output buffer.
    myListener.Flush();
    ```

## <a name="see-also"></a><span data-ttu-id="8a955-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8a955-124">See also</span></span>

- [<span data-ttu-id="8a955-125">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="8a955-125">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
- [<span data-ttu-id="8a955-126">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="8a955-126">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="8a955-127">Практическое руководство. Добавление операторов трассировки в код приложения</span><span class="sxs-lookup"><span data-stu-id="8a955-127">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="8a955-128">Трассировка и инструментирование приложений</span><span class="sxs-lookup"><span data-stu-id="8a955-128">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
