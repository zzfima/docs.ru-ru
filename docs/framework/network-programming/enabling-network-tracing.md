---
title: "Включение сетевой трассировки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "трассировка назначений"
  - "отправка трассировок в файл журнала"
  - "прослушиватели трассировки, сетевая трассировка"
  - "сетевая трассировка, включение"
  - "Отладчик CLR"
  - "прослушиватели по умолчанию"
  - "журналы, трассировка"
  - "назначение для выходных данных трассировки"
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Включение сетевой трассировки
Трассировка сети предоставляет доступ к сведениям о вызовах метода и сетевой трафик, созданный управляемым приложением.  Необходимо выполнить следующие задачи, чтобы включить трассировку сети в приложении:  
  
-   Компилировать код если включена трассировка.  См. раздел [How to: Compile Conditionally with Trace and Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) дополнительные сведения о параметрах компилятора, необходимое для включения трассировки.  
  
-   Укажите назначение для вывода данных трассировки.  
  
-   Настройка реакция на событие трассировки сети.  См. раздел [Практическое руководство. Настройте трассировку сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) подробные сведения.  
  
 Наиболее распространенные назначения трассировки прослушивателями трассировки, также называемых по умолчанию прослушиватель и файл журнала.  
  
 Трассировка по умолчанию использует прослушиватель если не задан прослушиватель трассировки.  Можно просматривать сообщения, отправляемые по умолчанию прослушивателю, выполнив код в управляемом код\- разрешенном отладчике, как отладчик среды CLR погруженный в пакет SDK платформы .NET Framework или DBwin32.exe погруженном с Windows SDK.  С помощью отладчика среды CLR, сообщения трассировки, отображаются в окне **Вывод**.  
  
 Если вы предпочитаете использовать файл для получения трассировок можно задать файл журнала с помощью параметров конфигурации, как показано в следующем примере.  \(Для общего обсуждение файлов конфигурации см. в разделе [файлы конфигурации](../../../docs/framework/configure-apps/index.md)\).  
  
 Отправлять трассировки в файл журнала, добавьте следующий узел к узлу `<system.diagnostics>` соответствующего файла конфигурации приложения или компьютера.  Можно изменить имя файла \(trace.log\) в соответствии с свои мере необходимости.  
  
```  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## См. также  
 [Интерпретация сетевой трассировки](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Трассировка сети в .NET Framework](../../../docs/framework/network-programming/network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/ru-ru/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)