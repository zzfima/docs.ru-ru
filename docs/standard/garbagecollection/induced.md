---
title: "Индуцированные коллекции"
description: "Индуцированные коллекции"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3e09b9dd-a800-4e56-b468-619f910ae22e
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: a10822518f0687dc7bbb06dd0fb77f6d9a3196fb

---

# <a name="induced-collections"></a>Индуцированные коллекции

В большинстве случаев сборщик мусора может определить самое подходящее время для выполнения сборки мусора, поэтому следует дать ему возможность работать независимо. В очень редких случаях принудительная сборка мусора может улучшить производительность приложения. В этих случаях можно вызвать сборку мусора с помощью метода [GC.Collect](xref:System.GC.Collect), чтобы принудительно начать сборку мусора. 

Используйте метод [Collect](xref:System.GC.Collect), если появилось заметное уменьшение в объеме памяти, используемом в определенной точке кода приложения. Например, если приложение использует сложное диалоговое окно, которое содержит несколько элементов управления, вызов [Collect](xref:System.GC.Collect) при закрытом диалоговом окне может улучшить производительность посредством немедленной очистки памяти, применяемой диалоговым окном. Убедитесь, что приложение не запускает сборку мусора слишком часто, потому что это может уменьшить производительность, если сборщик мусора непродуктивно пытается удалить объекты в не самое удачное время. Можно передать значение перечисления [GCCollectionMode.Optimized](xref:System.GCCollectionMode.Optimized) в метод [Collect](xref:System.GC.Collect), чтобы осуществлять сбор только в случае его эффективности, как описано в следующем разделе.

## <a name="gc-collection-mode"></a>Режим сборки мусора

Можно использовать одну из перегрузок метода [GC.Collect](xref:System.GC.Collect), которая включает значение [GCCollectionMode](xref:System.GCCollectionMode), для указания поведения принудительной сборки, как описано ниже.

Значение GCCollectionMode | Описание
---------------------- | ----------- 
[Default](xref:System.GCCollectionMode.Default) | Использует настройку сборки мусора по умолчанию для выполняемой версии платформы .NET Framework.
[Forced](xref:System.GCCollectionMode.Forced) | Вызывает немедленное выполнение принудительной сборки мусора. Это эквивалентно вызову перегрузки [GC.Collect()](xref:System.GC.Collect). В результате образуется коллекция полной блокировки всех поколений. Можно также уменьшить размер большой кучи объектов, присвоив свойству [GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode) значение [GCLargeObjectHeapCompactionMode.CompactOnce](xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce) до принудительного запуска немедленной блокирующей полной сборки мусора. 
[Optimized](xref:System.GCCollectionMode.Optimized) | Позволяет сборщику мусора определить, является ли текущий момент оптимальным для освобождения объектов. Сборщик мусора может определить, что сборка мусора будет недостаточно продуктивна, в этом случае он возвратится без удаления объектов.
 
## <a name="background-or-blocking-collections"></a>Фоновые или блокирующие сборки

Можно вызвать перегруженный метод [GC.Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)), чтобы указать, является ли индуцированная коллекция блокирующей или нет. Тип выполняемого методом *mode* сравнения зависит от значения параметра *blocking*. *mode* является членом перечисления [GCCollectionMode](xref:System.GCCollectionMode), а *blocking* является значением типа [Boolean](xref:System.Boolean). В следующей таблице приводится сводка по взаимодействию с аргументами mode и blocking. 

*mode* | *blocking* = true | *blocking* = false
------ | ----------------- | ------------------
[Forced](xref:System.GCCollectionMode.Forced) или [Default](xref:System.GCCollectionMode.Default) | Блокирующий сбор выполнится, как только это станет возможным. Если фоновая сборка выполняется и поколение равно 0 или 1, метод [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) немедленно активирует блокирующую сборку и возвращает управление по завершении сборки. Если фоновая сборка выполняется и параметр generation равен 2, метод дожидается завершения фоновой сборки, активирует блокирующую сборку поколения 2 и возвращает управление. | Сборка выполнится, как только это станет возможным. Метод [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) запрашивает фоновую сборку, однако это не гарантированно. В зависимости от обстоятельств блокирующая коллекция может выполняться. Если фоновая сборка уже выполняется, метод возвращает управление немедленно. 
[Optimized](xref:System.GCCollectionMode.Optimized) | Заблокированная коллекция может быть выполнена в зависимости от состояния сборщика мусора и параметра generation. Сборщик мусора пытается обеспечить оптимальную производительность. | Сборка может быть выполнена в зависимости от состояния сборщика мусора. Метод [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) запрашивает фоновую сборку, однако это не гарантированно. В зависимости от обстоятельств блокирующая коллекция может выполняться. Сборщик мусора пытается обеспечить оптимальную производительность. Если фоновая сборка уже выполняется, метод возвращает управление немедленно. 
 
## <a name="see-also"></a>См. также

[Режимы задержки](latency.md)

[Сборка мусора в .NET](index.md)



<!--HONumber=Nov16_HO1-->


