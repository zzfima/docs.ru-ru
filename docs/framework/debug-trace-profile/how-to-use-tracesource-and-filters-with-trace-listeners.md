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
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a>Практическое руководство. Использование TraceSource и фильтров с прослушивателями трассировки
Одной из новых функций в платформе .NET Framework версии 2.0 является расширенная система трассировки. Основное условие осталось неизменным: сообщения трассировки отправляются через переключатели к прослушивателям, которые передают данные соответствующему выходному носителю. Для версии 2.0 основное отличие заключается в том, что трассировку можно инициировать через экземпляры класса <xref:System.Diagnostics.TraceSource>. Класс <xref:System.Diagnostics.TraceSource> представляет собой улучшенную систему трассировки и может использоваться вместо статических методов более старых классов трассировки <xref:System.Diagnostics.Trace> и <xref:System.Diagnostics.Debug>. Знакомые классы <xref:System.Diagnostics.Trace> и <xref:System.Diagnostics.Debug> сохранены, но для трассировки рекомендуется использовать класс <xref:System.Diagnostics.TraceSource>.  
  
 В этом разделе описано использование <xref:System.Diagnostics.TraceSource> вместе с файлом конфигурации приложения.  Возможно, хотя и не рекомендуется, выполнять трассировку с помощью <xref:System.Diagnostics.TraceSource> без использования файла конфигурации. Сведения о трассировке без использования файла конфигурации см. в разделе [Практическое руководство. Создание и инициализация источников трассировки](how-to-create-and-initialize-trace-sources.md).  
  
### <a name="to-create-and-initialize-your-trace-source"></a>Создание и инициализация источника трассировки  
  
1. Первый шаг для инструментирования приложения с трассировкой — создание источника трассировки. В крупных проектах с различными компонентами можно создать отдельный источник трассировки для каждого компонента. Рекомендуется использовать имя приложения в качестве имени источника трассировки. Это поможет различить отдельные трассировки. В следующем коде создается новый источник трассировки (`mySource)`) и вызывается метод (`Activity1`), отслеживающий события.  Сообщения трассировки записываются прослушивателем трассировки по умолчанию.  
  
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
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a>Создание и инициализация прослушивателей трассировки и фильтров  
  
1. Код в первой процедуре не идентифицирует прослушиватели трассировки и фильтры программными средствами. Этот код только записывает сообщения трассировки в прослушиватель трассировки по умолчанию. Чтобы настроить конкретные прослушиватели трассировки и их связанные фильтры, измените файл конфигурации, соответствующий имени приложения. В этом файле можно добавить или удалить прослушиватель и установить свойства и фильтр для прослушивателя. В следующем примере файла конфигурации показано, как инициализировать прослушиватель трассировки с выводом данных на консоль и прослушиватель трассировки с записью в текстовый файл для источника трассировки, созданного на предыдущем шаге. Помимо настройки прослушивателей трассировки файл конфигурации также создает фильтры для обоих типов прослушивателей и переключатель источника для источника трассировки. Демонстрируются два приема для добавления прослушивателей трассировки: добавление прослушивателя непосредственно в источник трассировки, и добавление прослушивателя к общей коллекции прослушивателей, а затем добавление его по имени в источник трассировки. Фильтры, определенные для этих двух прослушивателей, инициализируются с различными уровнями источника. Это приводит к тому, что некоторые сообщения записываются только одним из двух прослушивателей.  
  
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
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a>Изменение уровня записи сообщения трассировки для прослушивателя  
  
1. Файл конфигурации инициализирует настройки для источника трассировки во время инициализации приложения. Чтобы изменить эти параметры, необходимо изменить файл конфигурации и перезапустить приложение или обновить приложение программными средствами с помощью метода <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>. Приложение может динамически изменить набор свойств с помощью файла конфигурации, чтобы переопределить любые настройки, заданные пользователем.  Например, может потребоваться, чтобы важные сообщения всегда отправлялись в текстовый файл, независимо от текущих параметров конфигурации.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [Практическое руководство. Создание и инициализация источников трассировки](how-to-create-and-initialize-trace-sources.md)
- [Прослушиватели трассировки](trace-listeners.md)
