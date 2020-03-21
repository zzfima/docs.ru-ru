---
title: Практическое руководство. Создание и инициализация источников трассировки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
ms.openlocfilehash: eeccad44bd2719a3cb2a721ba4e32a7bf477636f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174736"
---
# <a name="how-to-create-and-initialize-trace-sources"></a><span data-ttu-id="bcee5-102">Практическое руководство. Создание и инициализация источников трассировки</span><span class="sxs-lookup"><span data-stu-id="bcee5-102">How to: Create and Initialize Trace Sources</span></span>
<span data-ttu-id="bcee5-103">Класс <xref:System.Diagnostics.TraceSource> используется приложениями для создания трассировок, которые могут быть связаны с приложением.</span><span class="sxs-lookup"><span data-stu-id="bcee5-103">The <xref:System.Diagnostics.TraceSource> class is used by applications to produce traces that can be associated with the application.</span></span> <span data-ttu-id="bcee5-104"><xref:System.Diagnostics.TraceSource> предоставляет методы трассировки, позволяющие легко трассировать события, трассировать данные и выпускать информационные трассировки.</span><span class="sxs-lookup"><span data-stu-id="bcee5-104"><xref:System.Diagnostics.TraceSource> provides tracing methods that allow you to easily trace events, trace data, and issue informational traces.</span></span> <span data-ttu-id="bcee5-105">Выходные данные трассировки из объектов <xref:System.Diagnostics.TraceSource> можно создавать и инициализировать с использованием или без использования файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcee5-105">Trace output from <xref:System.Diagnostics.TraceSource> can be created and initialized with or without the use of configuration files.</span></span> <span data-ttu-id="bcee5-106">В этом разделе содержатся инструкции для обоих вариантов.</span><span class="sxs-lookup"><span data-stu-id="bcee5-106">This topic provides instructions for both options.</span></span> <span data-ttu-id="bcee5-107">Однако рекомендуется использовать файлы конфигурации для упрощения повторной настройки трассировки, создаваемой источниками трассировки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bcee5-107">However, we recommend that you use configuration files to facilitate the reconfiguration of the traces produced by trace sources at run time.</span></span>  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a><span data-ttu-id="bcee5-108">Создание и инициализация источника трассировки с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bcee5-108">To create and initialize a trace source using a configuration file</span></span>  
  
1. <span data-ttu-id="bcee5-109">Создайте проект приложения для консоли Visual Studio (.NET Framework) и замените поставляемый код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="bcee5-109">Create a Visual Studio console application project (.NET Framework) and replace the supplied code with the following code.</span></span> <span data-ttu-id="bcee5-110">Этот код регистрирует ошибки и предупреждения, выводит некоторые из них на консоль, а некоторые в файл myListener, созданный записями в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcee5-110">This code logs errors and warnings and outputs some of them to the console, and some of them to the myListener file that is created by the entries in the configuration file.</span></span>  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2. <span data-ttu-id="bcee5-111">Добавьте в проект файл конфигурации приложения (если его еще нет), чтобы инициализировать источник трассировки с именем `TraceSourceApp` в примере кода из шага 1.</span><span class="sxs-lookup"><span data-stu-id="bcee5-111">Add an application configuration file, if one is not present, to the project to initialize the trace source named `TraceSourceApp` in the code example in step 1.</span></span>  
  
3. <span data-ttu-id="bcee5-112">Замените содержимое файла конфигурации по умолчанию приведенными ниже параметрами, чтобы инициализировать прослушиватель трассировки с выводом данных на консоль и прослушиватель трассировки с записью в текстовый файл для источника трассировки, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="bcee5-112">Replace the default configuration file content with the following settings to initialize a console trace listener and a text writer trace listener for the trace source that was created in step 1.</span></span>  
  
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
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
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
  
     <span data-ttu-id="bcee5-113">Помимо настройки прослушивателей трассировки, файл конфигурации также создает фильтры для обоих типов прослушивателей и создает переключатель источника для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="bcee5-113">In addition to configuring the trace listeners, the configuration file creates filters for both listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="bcee5-114">Демонстрируются два приема для добавления прослушивателей трассировки: добавление прослушивателя непосредственно в источник трассировки, и добавление прослушивателя к общей коллекции прослушивателей, а затем добавление его по имени в источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="bcee5-114">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="bcee5-115">Фильтры, определенные для этих двух прослушивателей, инициализируются с различными уровнями источника.</span><span class="sxs-lookup"><span data-stu-id="bcee5-115">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="bcee5-116">Это приводит к тому, что некоторые сообщения записываются только одним из двух прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="bcee5-116">This results in some messages being written by only one of the two listeners.</span></span>  
  
     <span data-ttu-id="bcee5-117">Файл конфигурации инициализирует настройки для источника трассировки во время инициализации приложения.</span><span class="sxs-lookup"><span data-stu-id="bcee5-117">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="bcee5-118">Приложение может динамически изменить набор свойств с помощью файла конфигурации, чтобы переопределить любые настройки, заданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="bcee5-118">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span> <span data-ttu-id="bcee5-119">Например, может потребоваться, чтобы важные сообщения всегда отправлялись в текстовый файл, независимо от текущих настроек конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcee5-119">For example, you might want to ensure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span> <span data-ttu-id="bcee5-120">В примере кода показано, как переопределить параметры файла конфигурации таким образом, чтобы обеспечить вывод важных сообщений в прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="bcee5-120">The example code demonstrates how to override configuration file settings to ensure that critical messages are output to the trace listeners.</span></span>  
  
     <span data-ttu-id="bcee5-121">При изменении настроек файла конфигурации во время работы приложения начальные настройки не изменяются.</span><span class="sxs-lookup"><span data-stu-id="bcee5-121">Changing the configuration file settings while the application is executing does not change the initial settings.</span></span> <span data-ttu-id="bcee5-122">Чтобы изменить эти параметры, необходимо либо перезапустить приложение, либо обновить приложение программными средствами с помощью метода <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bcee5-122">To change the settings, you must either restart the application or programmatically refresh the application by using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a><span data-ttu-id="bcee5-123">Инициализация источников трассировки, прослушивателей и фильтров без файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bcee5-123">To initialize trace sources, listeners, and filters without a configuration file</span></span>  
  
- <span data-ttu-id="bcee5-124">Используйте следующий пример кода, чтобы разрешить трассировку через источник трассировки с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcee5-124">Use the following example code to enable tracing through a trace source without using a configuration file.</span></span> <span data-ttu-id="bcee5-125">Как правило, использование этого приема не рекомендовано, однако в некоторых обстоятельствах требуется инициализация трассировки независимо от файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcee5-125">This is not a recommended practice, but there may be circumstances in which you do not want to depend on configuration files to ensure tracing.</span></span>  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bcee5-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bcee5-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="bcee5-127">Трассировка и оборудование приложений</span><span class="sxs-lookup"><span data-stu-id="bcee5-127">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
