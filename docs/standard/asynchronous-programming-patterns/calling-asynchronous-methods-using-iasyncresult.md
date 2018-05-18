---
title: Вызов асинхронных методов с помощью IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25134e14154cceae3c11de531f38fe4530892492
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Вызов асинхронных методов с помощью IAsyncResult
Типы в .NET Framework и библиотеках классов сторонних разработчиков могут предоставлять методы, позволяющие приложению продолжать работу при выполнении асинхронных операций в потоках, отличных от основного потока приложения. В следующих разделах описаны и предоставлены примеры кода, которые демонстрируют разные способы вызова асинхронных методов, соответствующих шаблону проектирования <xref:System.IAsyncResult>.  
  
-   [Блокировка выполнения приложения путем завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   [Блокировка выполнения приложения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
-   [Запрос состояния асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
