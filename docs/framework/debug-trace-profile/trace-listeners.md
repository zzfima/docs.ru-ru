---
title: Прослушиватели трассировки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
ms.openlocfilehash: a51c046a296fbb62d21c7784cf7c1e78b700f3e9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216141"
---
# <a name="trace-listeners"></a>Прослушиватели трассировки
При использовании классов **Trace**, **Debug** и <xref:System.Diagnostics.TraceSource> необходимо обеспечить механизм сбора и записи отправляемых сообщений. Сообщения трассировки получаются *прослушивателями*. Цель прослушивателя — сбор, хранение и маршрутизация сообщений трассировки. Прослушиватели направляют вывод трассировки в соответствующий целевой объект, например журнал, окно или текстовый файл.  
  
 Прослушиватели доступны для классов **Debug**, **Trace** и <xref:System.Diagnostics.TraceSource>, каждый из которых может отправлять свои выходные данные разным объектам прослушивателей. Ниже перечислены часто используемые предварительно определенные прослушиватели.  
  
- Прослушиватель <xref:System.Diagnostics.TextWriterTraceListener> перенаправляет выходные данные в экземпляр класса <xref:System.IO.TextWriter> или любой объект, являющийся классом <xref:System.IO.Stream>. Он также может осуществлять запись в консоль или файл, потому что это классы <xref:System.IO.Stream>.  
  
- Класс <xref:System.Diagnostics.EventLogTraceListener> перенаправляет выходные данные в журнал событий.  
  
- Класс <xref:System.Diagnostics.DefaultTraceListener> выводит сообщения методов **Write** и **WriteLine** в строку **OutputDebugString** и метод **Debugger.Log**. В Visual Studio в этом случае сообщения отладки отображаются в окне «Вывод». Сообщения метода **Fail** и завершившегося сбоем метода **Assert** также выводятся в API Windows **OutputDebugString** и методе **Debugger.Log**. Также в этом случае отображается поле сообщений. Данное поведение — это поведение по умолчанию для сообщений **Debug** и **Trace**, так как прослушиватель **DefaultTraceListener** автоматически включается в каждую коллекцию `Listeners` и является единственным автоматически включаемым прослушивателем.  
  
- Объект <xref:System.Diagnostics.ConsoleTraceListener> направляет выходные данные трассировки или отладки в стандартный вывод или стандартный поток ошибок.  
  
- Прослушиватель <xref:System.Diagnostics.DelimitedListTraceListener> направляет выходные данные трассировки или отладки в модуль записи текста, например модуль записи в поток, или в поток, например файловый поток. Выходные данные трассировки имеют текстовый формат с разделителями, в котором используется разделитель, заданный свойством <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>.  
  
- Прослушиватель <xref:System.Diagnostics.XmlWriterTraceListener> направляет вывод отладки или трассировки в качестве кодированных в XML данных в метод <xref:System.IO.TextWriter> или поток <xref:System.IO.Stream>, например <xref:System.IO.FileStream>.  
  
 Если нужно, чтобы какой-либо еще прослушиватель, помимо <xref:System.Diagnostics.DefaultTraceListener>, получал выходные данные **Debug**, **Trace** и <xref:System.Diagnostics.TraceSource>, необходимо добавить его в коллекцию `Listeners`. Дополнительные сведения см. в разделе [Практическое руководство. Создание и инициализация прослушивателей трассировки](how-to-create-and-initialize-trace-listeners.md) и [Практическое руководство. Использование TraceSource и фильтров с прослушивателями трассировки](how-to-use-tracesource-and-filters-with-trace-listeners.md). Любой прослушиватель из коллекции **Listeners** получает те же сообщения от методов вывода трассировки. Предположим, например, что настроены два прослушивателя: **TextWriterTraceListener** и **EventLogTraceListener**. Каждый прослушиватель получает одно и то же сообщение. Прослушиватель **TextWriterTraceListener** направляет выходные данные в поток, а **EventLogTraceListener** направляет выходные данные в журнал событий.  
  
 В приведенном ниже примере показана отправка выходных данных в коллекцию **прослушивателей**.  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 При отладке и трассировке используется одна и та же коллекция **прослушивателей**, поэтому если добавить объект прослушивателя в коллекцию **Debug.Listeners** в приложении, он также будет добавлен и в коллекцию **Trace.Listeners**.  
  
 В следующем примере показано использование прослушивателя для отправки сведений трассировки на консоль.  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a>Прослушиватели, определяемые разработчиками  
 Можно определить собственные прослушиватели путем наследования от базового класса **TraceListener** и переопределения его методов своими пользовательскими методами. Дополнительные сведения о создании прослушивателей, определяемых разработчиками, см. в описании <xref:System.Diagnostics.TraceListener> в справочнике по .NET Framework.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [Трассировка и инструментирование приложений](tracing-and-instrumenting-applications.md)
- [Переключатели трассировки](trace-switches.md)
