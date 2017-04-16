---
title: "Asynchronous Programming Patterns | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "asynchronous design patterns, .NET Framework"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Asynchronous Programming Patterns
Платформа .NET Framework предоставляет три шаблона для выполнения асинхронных операций:  
  
-   шаблон асинхронной модели программирования \(АРМ\) \(также называемый шаблон <xref:System.IAsyncResult>\), где асинхронные операции требуют методов `Begin` и `End` \(например, асинхронные операции записи `BeginWrite` и `EndWrite`\).  Этот шаблон не рекомендуется использовать для разработки новых приложений.  Для получения дополнительной информации см. [Asynchronous Programming Model \(APM\)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).  
  
-   На основе событий асинхронного шаблона \(EAP\), который требует метод с суффиксом `Async`, а также требует одного или нескольких событий, типов делегата обработчика событий и производных типов `EventArg`.  Протокол EAP был введен в платформа.NET Framework 2.0.  Не рекомендуется для новых разработок.  Для получения дополнительной информации см. [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
-   Асинхронный шаблон на основе задач \(TAP\), который использует один метод для запуска и завершения асинхронной операции.  Шаблон ТАР был введен в платформа.NET Framework 4 и рекомендуется для асинхронного программирования в платформа.NET Framework.  Ключевые слова [async](../Topic/async%20\(C%23%20Reference\).md) и [await](../Topic/await%20\(C%23%20Reference\).md) в C\#, а также операторы [Async](../Topic/Async%20\(Visual%20Basic\).md) и [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) в языке Visual Basic добавляют поддержку языка для ТАР.  Для получения дополнительной информации см. [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
## Сравнение шаблонов  
 Для быстрого сравнения, как с помощью трех шаблонов моделировать асинхронные операции, рассмотрим метод `Read`, который считывает указанный объем данных в предоставленный буфер, начиная с заданного смещения:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
 Аналог APM этого метода приведет к методам `BeginRead` и `EndRead`:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
 Аналог EAP будут предоставлять следующий набор типов и членов:  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
 Аналог TAP приведет к следующему одному методу `ReadAsync`:  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
 Для подробного обсуждения TAP, APM и EAP перейдите по ссылкам в следующем разделе.  
  
## Связанные разделы  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Asynchronous Programming Model \(APM\)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)|Описание устаревшей модели, использующей интерфейс <xref:System.IAsyncResult> для предоставления асинхронного поведения.  Этот шаблон не рекомендуется использовать для новых разработок.|  
|[Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)|Описание события устаревшие модели для предоставления асинхронного поведения.  Этот шаблон не рекомендуется использовать для новых разработок.|  
|[Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Описание новой асинхронной модели на основе пространства имен <xref:System.Threading.Tasks>.  Эта модель является рекомендуемым подходом для асинхронного программирования в NET Framework 4 и более поздних версиях.|