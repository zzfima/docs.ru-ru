---
title: Практическое руководство. Использование TraceSource и фильтров с прослушивателями трассировки
ms.date: 03/30/2017
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
ms.openlocfilehash: 53cdce767d437c47aab94e883381954f8cf70653
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215921"
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a><span data-ttu-id="c454d-102">Практическое руководство. Использование TraceSource и фильтров с прослушивателями трассировки</span><span class="sxs-lookup"><span data-stu-id="c454d-102">How to: Use TraceSource and Filters with Trace Listeners</span></span>
<span data-ttu-id="c454d-103">Одной из новых функций в платформе .NET Framework версии 2.0 является расширенная система трассировки.</span><span class="sxs-lookup"><span data-stu-id="c454d-103">One of the new features in the .NET Framework version 2.0 is an enhanced tracing system.</span></span> <span data-ttu-id="c454d-104">Основное условие осталось неизменным: сообщения трассировки отправляются через переключатели к прослушивателям, которые передают данные соответствующему выходному носителю.</span><span class="sxs-lookup"><span data-stu-id="c454d-104">The basic premise is unchanged: tracing messages are sent through switches to listeners, which report the data to an associated output medium.</span></span> <span data-ttu-id="c454d-105">Для версии 2.0 основное отличие заключается в том, что трассировку можно инициировать через экземпляры класса <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="c454d-105">A primary difference for version 2.0 is that traces can be initiated through instances of the <xref:System.Diagnostics.TraceSource> class.</span></span> <span data-ttu-id="c454d-106">Класс <xref:System.Diagnostics.TraceSource> представляет собой улучшенную систему трассировки и может использоваться вместо статических методов более старых классов трассировки <xref:System.Diagnostics.Trace> и <xref:System.Diagnostics.Debug>.</span><span class="sxs-lookup"><span data-stu-id="c454d-106"><xref:System.Diagnostics.TraceSource> is intended to function as an enhanced tracing system and can be used in place of the static methods of the older <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> tracing classes.</span></span> <span data-ttu-id="c454d-107">Знакомые классы <xref:System.Diagnostics.Trace> и <xref:System.Diagnostics.Debug> сохранены, но для трассировки рекомендуется использовать класс <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="c454d-107">The familiar <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> classes still exist, but the recommended practice is to use the <xref:System.Diagnostics.TraceSource> class for tracing.</span></span>  
  
 <span data-ttu-id="c454d-108">В этом разделе описано использование <xref:System.Diagnostics.TraceSource> вместе с файлом конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="c454d-108">This topic describes the use of a <xref:System.Diagnostics.TraceSource> coupled with an application configuration file.</span></span>  <span data-ttu-id="c454d-109">Возможно, хотя и не рекомендуется, выполнять трассировку с помощью <xref:System.Diagnostics.TraceSource> без использования файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c454d-109">It is possible, although not recommended, to trace using a <xref:System.Diagnostics.TraceSource> without the use of a configuration file.</span></span> <span data-ttu-id="c454d-110">Сведения о трассировке без использования файла конфигурации см. в разделе [Практическое руководство. Создание и инициализация источников трассировки](how-to-create-and-initialize-trace-sources.md).</span><span class="sxs-lookup"><span data-stu-id="c454d-110">For information on tracing without a configuration file, see [How to: Create and Initialize Trace Sources](how-to-create-and-initialize-trace-sources.md).</span></span>  
  
### <a name="to-create-and-initialize-your-trace-source"></a><span data-ttu-id="c454d-111">Создание и инициализация источника трассировки</span><span class="sxs-lookup"><span data-stu-id="c454d-111">To create and initialize your trace source</span></span>  
  
1. <span data-ttu-id="c454d-112">Первый шаг для инструментирования приложения с трассировкой — создание источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="c454d-112">The first step to instrumenting an application with tracing is to create a trace source.</span></span> <span data-ttu-id="c454d-113">В крупных проектах с различными компонентами можно создать отдельный источник трассировки для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="c454d-113">In large projects with various components, you can create a separate trace source for each component.</span></span> <span data-ttu-id="c454d-114">Рекомендуется использовать имя приложения в качестве имени источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="c454d-114">The recommended practice is to use the application name for the trace source name.</span></span> <span data-ttu-id="c454d-115">Это поможет различить отдельные трассировки.</span><span class="sxs-lookup"><span data-stu-id="c454d-115">This will make it easier to keep the different traces separate.</span></span> <span data-ttu-id="c454d-116">В следующем коде создается новый источник трассировки (`mySource)`) и вызывается метод (`Activity1`), отслеживающий события.</span><span class="sxs-lookup"><span data-stu-id="c454d-116">The following code creates a new trace source (`mySource)` and calls a method (`Activity1`) that traces events.</span></span>  <span data-ttu-id="c454d-117">Сообщения трассировки записываются прослушивателем трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c454d-117">The trace messages are written by the default trace listener.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a><span data-ttu-id="c454d-118">Создание и инициализация прослушивателей трассировки и фильтров</span><span class="sxs-lookup"><span data-stu-id="c454d-118">To create and initialize trace listeners and filters</span></span>  
  
1. <span data-ttu-id="c454d-119">Код в первой процедуре не идентифицирует прослушиватели трассировки и фильтры программными средствами.</span><span class="sxs-lookup"><span data-stu-id="c454d-119">The code in the first procedure does not programmatically identify any trace listeners or filters.</span></span> <span data-ttu-id="c454d-120">Этот код только записывает сообщения трассировки в прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c454d-120">The code alone results in the trace messages being written to the default trace listener.</span></span> <span data-ttu-id="c454d-121">Чтобы настроить конкретные прослушиватели трассировки и их связанные фильтры, измените файл конфигурации, соответствующий имени приложения.</span><span class="sxs-lookup"><span data-stu-id="c454d-121">To configure specific trace listeners and their associated filters, edit the configuration file that corresponds to the name of your application.</span></span> <span data-ttu-id="c454d-122">В этом файле можно добавить или удалить прослушиватель и установить свойства и фильтр для прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="c454d-122">In this file, you can add or remove a listener, set the properties and filter for a listener, or remove listeners.</span></span> <span data-ttu-id="c454d-123">В следующем примере файла конфигурации показано, как инициализировать прослушиватель трассировки с выводом данных на консоль и прослушиватель трассировки с записью в текстовый файл для источника трассировки, созданного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="c454d-123">The following configuration file example shows how to initialize a console trace listener and a text writer trace listener for the trace source that is created in the preceding procedure.</span></span> <span data-ttu-id="c454d-124">Помимо настройки прослушивателей трассировки файл конфигурации также создает фильтры для обоих типов прослушивателей и переключатель источника для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="c454d-124">In addition to configuring the trace listeners, the configuration file creates filters for both of the listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="c454d-125">Демонстрируются два приема для добавления прослушивателей трассировки: добавление прослушивателя непосредственно в источник трассировки, и добавление прослушивателя к общей коллекции прослушивателей, а затем добавление его по имени в источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="c454d-125">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="c454d-126">Фильтры, определенные для этих двух прослушивателей, инициализируются с различными уровнями источника.</span><span class="sxs-lookup"><span data-stu-id="c454d-126">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="c454d-127">Это приводит к тому, что некоторые сообщения записываются только одним из двух прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="c454d-127">This results in some messages being written by only one of the two listeners.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"   
            switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"   
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"   
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"   
            type="System.Diagnostics.TextWriterTraceListener"   
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a><span data-ttu-id="c454d-128">Изменение уровня записи сообщения трассировки для прослушивателя</span><span class="sxs-lookup"><span data-stu-id="c454d-128">To change the level at which a listener writes a trace message</span></span>  
  
1. <span data-ttu-id="c454d-129">Файл конфигурации инициализирует настройки для источника трассировки во время инициализации приложения.</span><span class="sxs-lookup"><span data-stu-id="c454d-129">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="c454d-130">Чтобы изменить эти параметры, необходимо изменить файл конфигурации и перезапустить приложение или обновить приложение программными средствами с помощью метода <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c454d-130">To change those settings you must change the configuration file and restart the application or programmatically refresh the application using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c454d-131">Приложение может динамически изменить набор свойств с помощью файла конфигурации, чтобы переопределить любые настройки, заданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="c454d-131">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span>  <span data-ttu-id="c454d-132">Например, может потребоваться, чтобы важные сообщения всегда отправлялись в текстовый файл, независимо от текущих параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c454d-132">For example, you might want to assure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified   
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =   
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures   
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners   
                // for all event types. This statement will override   
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,   
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,   
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c454d-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="c454d-133">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="c454d-134">Практическое руководство. Создание и инициализация источников трассировки</span><span class="sxs-lookup"><span data-stu-id="c454d-134">How to: Create and Initialize Trace Sources</span></span>](how-to-create-and-initialize-trace-sources.md)
- [<span data-ttu-id="c454d-135">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="c454d-135">Trace Listeners</span></span>](trace-listeners.md)
