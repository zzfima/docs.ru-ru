---
title: Очистка неуправляемых ресурсов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e32d2d4424d05b95af1eda400974da3293b8499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cleaning-up-unmanaged-resources"></a>Очистка неуправляемых ресурсов
Для большинства объектов, создаваемых приложением, управление памятью осуществляется сборщиком мусора .NET. Однако при создании объектов, которые включают неуправляемые ресурсы, после использования неуправляемых ресурсов в приложении необходимо освобождать их явно. Основным типом неуправляемых ресурсов являются объекты, заключающие в себе ресурсы операционной системы, такие как файлы, окна, сетевые подключения и подключения к базам данным. Хотя сборщик мусора может отслеживать время жизни управляемого объекта, инкапсулирующего неуправляемые ресурсы, он не имеет сведений о том, как освобождать такие ресурсы.  
  
 Если ваши типы используют неуправляемые ресурсы, необходимо выполнить следующие действия:  
  
-   Реализуйте [шаблон удаления](../../../docs/standard/design-guidelines/dispose-pattern.md). Это требует реализации <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> для детерминированного освобождения неуправляемых ресурсов. Объект-получатель типа вызывает метод <xref:System.IDisposable.Dispose%2A>, когда объект и используемые им ресурсы больше не нужны. Метод <xref:System.IDisposable.Dispose%2A> немедленно освобождает неуправляемые ресурсы.  
  
-   Предусмотрите освобождение неуправляемых ресурсов, в случае если метод <xref:System.IDisposable.Dispose%2A> не будет вызван объектом-получателем. Это можно сделать двумя способами.  
  
    -   Используйте безопасный дескриптор в качестве оболочки для неуправляемого ресурса. Это рекомендуемая методика. Безопасные дескрипторы являются производными от класса <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>. Они включают надежный метод <xref:System.Object.Finalize%2A>. При использовании безопасного дескриптора нужно просто реализовать интерфейс <xref:System.IDisposable> и вызвать метод <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> этого безопасного дескриптора в реализации <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Метод завершения безопасного дескриптора автоматически вызывается сборщиком мусора, если не вызывается метод <xref:System.IDisposable.Dispose%2A>.  
  
         —или—  
  
    -   Переопределите метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Завершение включает недетерминированное освобождение неуправляемых ресурсов, когда объекту-получателю типа не удается вызвать метод <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> для их детерминированного удаления. Однако поскольку завершение объекта может быть сложной операцией с высокой вероятностью ошибок, рекомендуется использовать безопасный дескриптор вместо указания собственного метода завершения.  
  
 Объекты-получатели типа могут затем вызвать реализацию <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> непосредственно для освобождения памяти, используемой неуправляемыми ресурсами. При правильной реализации метода <xref:System.IDisposable.Dispose%2A> метод <xref:System.Object.Finalize%2A> или переопределенная версия метода <xref:System.Object.Finalize%2A?displayProperty=nameWithType> становятся резервным средством очистки ресурсов в случае, если не вызывается метод <xref:System.IDisposable.Dispose%2A>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Реализация метода dispose](../../../docs/standard/garbage-collection/implementing-dispose.md)  
 Описание того, как реализовать [шаблон удаления](../../../docs/standard/design-guidelines/dispose-pattern.md) для освобождения неуправляемых ресурсов.  
  
 [Использование объектов, реализующих IDisposable](../../../docs/standard/garbage-collection/using-objects.md)  
 Описание того, как объекты-получатели типа обеспечивают вызов своей реализации метода <xref:System.IDisposable.Dispose%2A>. Для этого рекомендуется использовать оператор `using` (C# ) или `Using` (Visual Basic).  
  
## <a name="reference"></a>Ссылка  
 <xref:System.IDisposable?displayProperty=nameWithType>  
 Определяет метод <xref:System.IDisposable.Dispose%2A> для освобождения неуправляемых ресурсов.  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 Предусматривает завершение объекта, если неуправляемые ресурсы не освобождены методом <xref:System.IDisposable.Dispose%2A>.  
  
 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>  
 Отключает завершение. Этот метод обычно вызывается из метода `Dispose`, чтобы не допустить выполнения метода завершения.
