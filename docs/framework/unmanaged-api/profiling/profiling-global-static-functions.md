---
title: Глобальные статические функции профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860870"
---
# <a name="profiling-global-static-functions"></a>Глобальные статические функции профилирования
В этом разделе описываются неуправляемые функции API, используемые API профилирования.  
  
## <a name="in-this-section"></a>В этом разделе  
  
## <a name="net-framework-version-1-profiling-functions"></a>.NET Framework функции профилирования версии 1  
 [Функция FunctionEnter](functionenter-function.md)  
 Уведомляет профилировщик о передаче управления в функцию. Не рекомендуется использовать в .NET Framework 2,0.  
  
 [Функция FunctionLeave](functionleave-function.md)  
 Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту. Не рекомендуется использовать в .NET Framework 2,0.  
  
 [Функция FunctionTailcall](functiontailcall-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail. Не рекомендуется использовать в .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Функции профилирования .NET Framework версии 2  
 [Функция FunctionIDMapper](functionidmapper-function.md)  
 Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в обратных вызовах [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)и [FunctionTailcall2](functiontailcall2-function.md) для этой функции. Также позволяет профилировщику указать, требуется ли получать обратные вызовы для этой функции.  
  
 [Функция FunctionEnter2](functionenter2-function.md)  
 Уведомляет профилировщик о передаче управления в функцию и предоставляет сведения о кадре стека и аргументах функции. Не рекомендуется использовать в .NET Framework 4.  
  
 [Функция FunctionLeave2](functionleave2-function.md)  
 Уведомляет профилировщик о том, что функция собирается вернуться к вызывающему объекту, и предоставляет сведения о кадре стека и возвращаемом значении функции. Не рекомендуется использовать в .NET Framework 4.  
  
 [Функция FunctionTailcall2](functiontailcall2-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail и предоставляет сведения о кадре стека. Не рекомендуется использовать в .NET Framework 4.  
  
 [Функция StackSnapshotCallback](stacksnapshotcallback-function.md)  
 Предоставляет профилировщику сведения о каждом управляемом кадре и каждом запуске неуправляемых кадров в стеке во время прохода стека, который инициируется методом [ICorProfilerInfo2::D остаккснапшот](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="net-framework-version-4-profiling-functions"></a>Функции профилирования .NET Framework версии 4  
 [Функция FunctionIDMapper2](functionidmapper2-function.md)  
 Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в ответных вызовах [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)или[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) для этой функции. Также позволяет профилировщику указывать, хотят ли они получать обратные вызовы для этой функции.  
  
 `FunctionIDMapper2` расширяет функцию [FunctionIDMapper](functionidmapper-function.md) с помощью параметра `clientData`, который профилировщики могут использовать для устранения неоднозначности между средами выполнения.  
  
 [Функция FunctionEnter3](functionenter3-function.md)  
 Уведомляет профилировщик о передаче управления в функцию.  
  
 [Функция FunctionEnter3WithInfo](functionenter3withinfo-function.md)  
 Уведомляет профилировщик о передаче управления в функцию и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) для получения кадра стека и аргументов функции.  
  
 [Функция FunctionLeave3](functionleave3-function.md)  
 Уведомляет профилировщик о том, что управление возвращается из функции.  
  
 [Функция FunctionLeave3WithInfo](functionleave3withinfo-function.md)  
 Уведомляет профилировщик о том, что управление возвращается из функции, и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) для получения кадра стека и возвращаемого значения.  
  
 [Функция FunctionTailcall3](functiontailcall3-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.  
  
 [Функция FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail, и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) для получения кадра стека.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о профилировании](profiling-overview.md)  
  
 [Интерфейсы профилирования](profiling-interfaces.md)  
  
 [Перечисления профилирования](profiling-enumerations.md)  
  
 [Структуры профилирования](profiling-structures.md)
