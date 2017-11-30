---
title: "Включение сетевой трассировки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trace destinations
- sending traces to log file
- trace listeners, network tracing
- network tracing, enabling
- CLR Debugger
- default listeners
- logs, trace
- destination for tracing output
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: da6c9723849694a764a3cb1c050abdb447776113
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-network-tracing"></a>Включение сетевой трассировки
Трассировка сети предоставляет доступ к сведениям о вызовах методов и о сетевом трафике, созданном управляемым приложением. Чтобы включить трассировку сети в приложении, выполните следующие действия:  
  
-   Скомпилируйте код с включенной трассировкой. Дополнительные сведения о параметрах компилятора, которые требуются для включения трассировки, см. в разделе [Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
  
-   Укажите назначение для выходных данных трассировки.  
  
-   Настройте поведение трассировки сети. Дополнительные сведения см. в разделе [Практическое руководство. Настройка трассировки сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 Чаще всего в качестве назначений для трассировки сети (прослушивателей трассировки) выступают прослушиватели по умолчанию и файлы журнала.  
  
 Если прослушиватель трассировки не указан, используется прослушиватель по умолчанию. Вы можете просматривать сообщения, отправляемые в прослушиватель по умолчанию при выполнении кода в отладчике с поддержкой управляемого кода, такого как отладчик среды CLR из состава пакета .NET Framework SDK или DBwin32.exe из пакета Windows SDK. При использовании отладчика среды CLR сообщения трассировки появляются в окне **Выходные данные**.  
  
 Если вы хотите записывать результаты трассировки в файл, укажите файл журнала в параметрах конфигурации, как показано в следующем примере. (Общие сведения о файлах конфигурации см. в разделе [Файлы конфигурации](../../../docs/framework/configure-apps/index.md).)  
  
 Чтобы отправлять сообщения трассировки в файл журнала, добавьте следующий узел в узел `<system.diagnostics>` соответствующего файла конфигурации приложения или компьютера. При необходимости имя файла (trace.log) можно изменить.  
  
```xml  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>См. также  
 [Интерпретация сетевой трассировки](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Трассировка сети в .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 [Введение. Подготовка к инструментированию и трассировка](http://msdn.microsoft.com/en-us/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
