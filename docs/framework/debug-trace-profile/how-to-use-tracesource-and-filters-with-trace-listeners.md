---
title: "How to: Use TraceSource and Filters with Trace Listeners | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "initializing trace listeners"
  - "configuration files [.NET Framework], trace listeners"
  - "app.config files, trace listeners"
  - "levels of writing trace messages"
  - "trace listeners, TraceSource class"
  - "application configuration files, trace listeners"
  - "filters, trace listeners"
  - "TraceSource class, trace listeners"
  - "trace listeners, creating"
  - "trace listeners, filters"
  - "trace listeners, initializing"
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Use TraceSource and Filters with Trace Listeners
Одной из новых возможностей в .NET Framework версии 2.0 является расширенная система трассировки.  Основное условие осталось неизменным: сообщения трассировки отправляются через переключатели к прослушивателям, которые сообщают данные связанному носителю вывода.   Основное отличие версии 2.0 заключается в том, что трассировку можно инициировать через экземпляры класса <xref:System.Diagnostics.TraceSource>.  Класс <xref:System.Diagnostics.TraceSource> предназначен для использования в качестве улучшенной системы трассировки и может использоваться вместо статических методов применявшихся ранее классов трассировки <xref:System.Diagnostics.Trace> и <xref:System.Diagnostics.Debug>.  Знакомые классы <xref:System.Diagnostics.Trace> и <xref:System.Diagnostics.Debug> все еще существуют, но рекомендуется использование класса <xref:System.Diagnostics.TraceSource> для трассировки.  
  
 В данном разделе описано использование <xref:System.Diagnostics.TraceSource> в сочетании с файлом конфигурации приложения.  Можно выполнять трассировку с помощью <xref:System.Diagnostics.TraceSource> без использования файла конфигурации, хотя это не рекомендуется.  Дополнительные сведения по выполнению трассировки без использования файла конфигурации см. в разделе [Практическое руководство. Создание и инициализация источников трассировки](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md).  
  
### Создание и инициализация источника трассировки  
  
1.  Первым шагом для инструментирования приложения с трассировкой является создание источника трассировки.  В крупных проектах с различными компонентами можно создать отдельный источник трассировки для каждого компонента.  В качестве имени источника трассировки рекомендуется использовать имя приложения.  Благодаря этому проще хранить различные трассировки отдельно.  В следующем коде создается новый источник трассировки \(`mySource)` и вызывается метод \(`Activity1`\), отслеживающий события.  Сообщения трассировки записываются прослушивателем трассировки, назначенным по умолчанию.  
  
    ```  
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
  
### Создание и инициализация прослушивателей трассировки и фильтров  
  
1.  Код в первой процедуре не идентифицирует прослушиватели трассировки и фильтры программными средствами.   Результатом кода в исходном виде является запись сообщений трассировки прослушивателем трассировки, назначенным по умолчанию.  Чтобы настроить конкретные прослушиватели трассировки и их связанные фильтры, измените файл конфигурации, соответствующий имени приложения.  В этом файле можно добавить или удалить прослушиватель, задать для прослушивателя свойства и фильтр, или удалить прослушиватели.  В следующем файле конфигурации показано, как инициализировать прослушиватель трассировки консоли и прослушиватель трассировки средства записи текста для источника трассировки, созданного в предыдущей процедуре.  Помимо настройки прослушивателей трассировки, файл конфигурации создает фильтры для обоих типов прослушивателей и создает переключатель источника для источника трассировки.  Демонстрируются два приема для добавления прослушивателей трассировки: добавление прослушивателя непосредственно в источник трассировки, и добавление прослушивателя к общей коллекции прослушивателей, а затем добавление его по имени в источник трассировки.  Фильтры, определенные для этих двух прослушивателей, инициализируются с различными уровнями источника.  Это приводит к тому, что некоторые сообщения записываются только одним из двух прослушивателей.  
  
    ```  
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
  
### Изменение уровня, на котором прослушиватель записывает сообщение трассировки  
  
1.  Файл конфигурации инициализирует настройки для источника трассировки во время инициализации приложения.  Чтобы изменить данные настройки, необходимо изменить файл конфигурации и перезапустить приложение, либо обновить приложение программными средствами с помощью метода <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName>.  Приложение может динамически изменить набор свойств с помощью файла конфигурации, чтобы переопределить любые настройки, заданные пользователем.  Например, может потребоваться, чтобы важные сообщения всегда отправлялись в текстовый файл, независимо от текущих настроек конфигурации.  
  
    ```  
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
  
## См. также  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventTypeFilter>   
 [Практическое руководство. Создание и инициализация источников трассировки](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)