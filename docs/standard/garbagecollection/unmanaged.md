---
title: "Очистка неуправляемых ресурсов"
description: "Очистка неуправляемых ресурсов"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8c97c3e2-8619-47ce-ae29-d6a3140bfa83
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: 692916bc5a9afd55dc4e3d0249386d2e3750895f

---

# <a name="cleaning-up-unmanaged-resources"></a>Очистка неуправляемых ресурсов

Для большинства объектов, создаваемых приложением, управление памятью осуществляется сборщиком мусора .NET. Однако при создании объектов, которые включают неуправляемые ресурсы, после использования неуправляемых ресурсов в приложении необходимо освобождать их явно. Основным типом неуправляемых ресурсов являются объекты, заключающие в себе ресурсы операционной системы, такие как файлы, окна, сетевые подключения и подключения к базам данным. Хотя сборщик мусора может отслеживать время жизни управляемого объекта, инкапсулирующего неуправляемые ресурсы, он не имеет сведений о том, как освобождать такие ресурсы. 

Если ваши типы используют неуправляемые ресурсы, необходимо выполнить следующие действия: 

* Реализуйте шаблон удаления. Для этого необходимо реализовать интерфейс [IDisposable.Dispose](xref:System.IDisposable.Dispose) для детерминированного освобождения неуправляемых ресурсов. Объект-получатель типа вызывает метод [Dispose](xref:System.IDisposable.Dispose), когда объект и используемые им ресурсы больше не нужны. Метод [Dispose](xref:System.IDisposable.Dispose) немедленно освобождает неуправляемые ресурсы. 

* Предусмотрите освобождение неуправляемых ресурсов, в случае если метод [Dispose](xref:System.IDisposable.Dispose) не будет вызван объектом-получателем. Это можно сделать двумя способами. 

    * Используйте безопасный дескриптор в качестве оболочки для неуправляемого ресурса. Это рекомендуемая методика. Безопасные дескрипторы являются производными от класса [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle). Они включают надежный метод [Finalize](xref:System.Object.Finalize). При использовании безопасного дескриптора нужно просто реализовать интерфейс [IDisposable](xref:System.IDisposable) и вызвать метод [Dispose](xref:System.IDisposable.Dispose) этого безопасного дескриптора в реализации [IDisposable.Dispose](xref:System.IDisposable.Dispose). Метод завершения безопасного дескриптора автоматически вызывается сборщиком мусора, если не вызывается метод [Dispose](xref:System.IDisposable.Dispose). 

      —или—

    * Переопределите метод [Object.Finalize](xref:System.Object.Finalize). Завершение включает недетерминированное освобождение неуправляемых ресурсов, когда объекту-получателю типа не удается вызвать метод [IDisposable.Dispose](xref:System.IDisposable.Dispose) для их детерминированного удаления. Однако поскольку завершение объекта может быть сложной операцией с высокой вероятностью ошибок, рекомендуется использовать безопасный дескриптор вместо указания собственного метода завершения. 

Объекты-получатели типа могут затем вызвать реализацию [IDisposable.Dispose](xref:System.IDisposable.Dispose) непосредственно для освобождения памяти, используемой неуправляемыми ресурсами. При правильной реализации метода [Dispose](xref:System.IDisposable.Dispose) метод [Finalize](xref:System.Object.Finalize) или переопределенная версия метода [Object.Finalize](xref:System.Object.Finalize) становятся резервным средством очистки ресурсов в случае, если не вызывается метод [Dispose](xref:System.IDisposable.Dispose). 

## <a name="in-this-section"></a>Содержание

[Реализация метода dispose](implementing-dispose.md) — описание способа реализации шаблона удаления для освобождения неуправляемых ресурсов.

[Использование объектов, реализующих IDisposable](using-objects.md) — описание того, как объекты-получатели типа обеспечивают вызов своей реализации метода Dispose. Для этого рекомендуется использовать оператор using (C# ) или Using (Visual Basic).

## <a name="reference"></a>Ссылки

[System.IDisposable](xref:System.IDisposable) — определяет метод `Dispose` для освобождения неуправляемых ресурсов.

[Object.Finalize](xref:System.Object.Finalize) — предусматривает завершение объекта, если неуправляемые ресурсы не освобождены методом `Dispose`. 

[GC.SuppressFinalize](xref:System.GC#System_GC_SuppressFinalize_System_Object_) — отключает завершение. Этот метод обычно вызывается из метода `Dispose`, чтобы не допустить выполнения метода завершения. 



<!--HONumber=Nov16_HO1-->


