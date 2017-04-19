---
title: "Шаблоны асинхронного программирования | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 26d5c4da21671c0f4ce37bf08c28ae82213f4374
ms.lasthandoff: 04/08/2017

---
# <a name="asynchronous-programming-patterns"></a>Шаблоны асинхронного программирования
Платформа .NET Framework предоставляет три шаблона для выполнения асинхронных операций:  
  
-   Шаблон асинхронной модели программирования (АРМ) (также называемый шаблон <xref:System.IAsyncResult>), где асинхронные операции требуют методов `Begin` и `End` (например, асинхронные операции записи `BeginWrite` и `EndWrite`). Этот шаблон не рекомендуется использовать для разработки новых приложений. Дополнительные сведения см. в статье [Асинхронная модель программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).  
  
-   На основе событий асинхронного шаблона (EAP), который требует метод с суффиксом `Async`, а также требует одного или нескольких событий, типов делегата обработчика событий и производных типов `EventArg`. Протокол EAP был введен в платформа.NET Framework 2.0. Не рекомендуется для новых разработок. Дополнительные сведения см. в разделе [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
-   Асинхронный шаблон на основе задач (TAP), который использует один метод для запуска и завершения асинхронной операции. Шаблон ТАР был введен в платформа.NET Framework 4 и рекомендуется для асинхронного программирования в платформа.NET Framework. Ключевые слова [async](~/docs/csharp/language-reference/keywords/async.md) и [await](~/docs/csharp/language-reference/keywords/await.md) в C#, а также операторы [Async](~/docs/visual-basic/language-reference/modifiers/async.md) и [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) в языке Visual Basic добавляют поддержку языка для ТАР. Дополнительные сведения см. в разделе [Асинхронный шаблон, основанный на задачах (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
## <a name="comparing-patterns"></a>Сравнение шаблонов  
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
  
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Асинхронная модель программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)|Описание устаревшей модели, использующей интерфейс <xref:System.IAsyncResult> для предоставления асинхронного поведения. Этот шаблон не рекомендуется использовать для новых разработок.|  
|[Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)|Описание события устаревшие модели для предоставления асинхронного поведения. Этот шаблон не рекомендуется использовать для новых разработок.|  
|[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))|Описание новой асинхронной модели на основе пространства имен <xref:System.Threading.Tasks>. Эта модель является рекомендуемым подходом для асинхронного программирования в NET Framework 4 и более поздних версиях.|
