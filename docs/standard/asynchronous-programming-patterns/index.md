---
title: Шаблоны асинхронного программирования
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: dfce69ee18b8346cd802b4934de63bf0a39c72f0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124260"
---
# <a name="asynchronous-programming-patterns"></a>Шаблоны асинхронного программирования

В .NET есть три шаблона для выполнения асинхронных операций:  

- **Асинхронный шаблон на основе задач (TAP)** , который использует один метод для запуска и завершения асинхронной операции. Шаблон TAP был реализован в .NET Framework 4. **Именно его рекомендуется использовать для асинхронного программирования в .NET**. Ключевые слова [async](../../csharp/language-reference/keywords/async.md) и [await](../../csharp/language-reference/operators/await.md) в C#, а также операторы [Async](../../visual-basic/language-reference/modifiers/async.md) и [Await](../../visual-basic/language-reference/operators/await-operator.md) в Visual Basic добавляют для TAP поддержку языка. Дополнительные сведения см. в разделе [Асинхронный шаблон, основанный на задачах (TAP)](task-based-asynchronous-pattern-tap.md).  

- **Асинхронная модель на основе событий (EAP)** . Это устаревшая модель на основе событий, обеспечивающая работу в асинхронном режиме. Для нее требуется метод с суффиксом `Async`, одно или несколько событий, типы делегатов обработчика событий и производные типы `EventArg`. Протокол EAP был введен в платформа.NET Framework 2.0. Ее не рекомендуется использовать для новых разработок. Дополнительные сведения см. в разделе [Асинхронная модель на основе событий (EAP)](event-based-asynchronous-pattern-eap.md).  

- **Модель асинхронного программирования (APM)** (также называется шаблоном <xref:System.IAsyncResult>). Это устаревшая модель, в которой для реализации асинхронного поведения используется интерфейс <xref:System.IAsyncResult>. В этом шаблоне для синхронных операций требуются методы `Begin` и `End` (например, `BeginWrite` и `EndWrite` позволяют реализовать асинхронную операцию записи). Этот шаблон не рекомендуется использовать для разработки новых приложений. Дополнительные сведения см. в статье [Асинхронная модель программирования (APM)](asynchronous-programming-model-apm.md).  
  
## <a name="comparison-of-patterns"></a>Сравнение шаблонов

Для быстрого сравнения, как с помощью трех шаблонов моделировать асинхронные операции, рассмотрим метод `Read`, который считывает указанный объем данных в предоставленный буфер, начиная с заданного смещения:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

Этот же метод с использованием TAP предоставит такой метод `ReadAsync`:  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
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
  
Этот же метод с APM предоставит методы `BeginRead` и `EndRead`:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a>См. также

- [Подробный обзор асинхронного программирования](../async-in-depth.md)
- [Асинхронное программирование на C#](../../csharp/async.md)
- [Асинхронное программирование на F#](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)
