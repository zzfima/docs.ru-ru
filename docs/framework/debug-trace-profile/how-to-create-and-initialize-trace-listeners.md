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
ms.openlocfilehash: ce0df0af32d6798c89c8db6761d18febc1c398bb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217446"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a>Практическое руководство. Создание и инициализация прослушивателей трассировки

Классы <xref:System.Diagnostics.Debug?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace?displayProperty=nameWithType> отправляют сообщения объектам, которые называются прослушивателями. Эти объекты получают и обрабатывают эти сообщения. Один из таких прослушивателей, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, автоматически создается и инициализируется при включении трассировки или отладки. Если требуется направить выходные данные типа <xref:System.Diagnostics.Trace> или <xref:System.Diagnostics.Debug> каким-либо дополнительным источникам, необходимо создать и инициализировать дополнительные прослушиватели трассировки.

Создаваемые прослушиватели должны соответствовать индивидуальным требованиям приложения. Например, если требуется текстовая запись всех выходных данных трассировки, создайте прослушиватель <xref:System.Diagnostics.TextWriterTraceListener>, который будет записывать все выходные данные в новый текстовый файл, если эта функция включена. С другой стороны, если требуется просмотреть выходные данные только во время исполнения приложения, создайте прослушиватель <xref:System.Diagnostics.ConsoleTraceListener>, направляющий все выходные данные в окно консоли. Прослушиватель <xref:System.Diagnostics.EventLogTraceListener> может направлять выходные данные трассировки в журнал событий. Дополнительные сведения см. в разделе [Прослушиватели трассировки](trace-listeners.md).

Можно создать прослушиватели трассировки в [файле конфигурации приложения](../configure-apps/index.md) или в собственном коде. Рекомендуется использовать файлы конфигурации приложения, так как они позволяют добавлять, изменять или удалять прослушиватели трассировки без внесения изменений в код.

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a>Создание и использование прослушивателя трассировки с использованием файла конфигурации

1. Объявите прослушиватель трассировки в файле конфигурации приложения. Если создаваемый прослушиватель требует какие-либо другие объекты, также объявите их. В следующем примере показано создание прослушивателя с именем `myListener`, записывающего данные в текстовый файл `TextWriterOutput.log`.

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

2. Используйте класс <xref:System.Diagnostics.Trace> в своем коде для записи сообщения в прослушиватели трассировки.

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

### <a name="to-create-and-use-a-trace-listener-in-code"></a>Создание и использование прослушивателя трассировки в коде

- Добавьте прослушиватель трассировки в коллекцию <xref:System.Diagnostics.Trace.Listeners%2A> и отправьте сведения трассировки прослушивателям.

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

    \- или -

- Если не нужно, чтобы прослушиватель получал выходные данные трассировки, не добавляйте его в коллекцию <xref:System.Diagnostics.Trace.Listeners%2A>. Допускается выдача выходных данных через прослушиватель независимо от коллекции <xref:System.Diagnostics.Trace.Listeners%2A> путем вызова собственных методов вывода прослушивателя. В следующем примере показано, как выполнить запись строки в прослушиватель, не являющийся частью коллекции <xref:System.Diagnostics.Trace.Listeners%2A>.

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

## <a name="see-also"></a>См. также:

- [Прослушиватели трассировки](trace-listeners.md)
- [Переключатели трассировки](trace-switches.md)
- [Практическое руководство. Добавление операторов трассировки в код приложения](how-to-add-trace-statements-to-application-code.md)
- [Трассировка и инструментирование приложений](tracing-and-instrumenting-applications.md)
