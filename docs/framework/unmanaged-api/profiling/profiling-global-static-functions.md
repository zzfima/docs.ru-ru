---
title: Глобальные статические функции профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: d1d9b0a4c61ce7c3f8f9792046fb4bddf0fdfa05
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447434"
---
# <a name="profiling-global-static-functions"></a>Глобальные статические функции профилирования
В этом разделе описываются неуправляемые функции API, используемые API профилирования.  
  
## <a name="in-this-section"></a>В этом разделе  
  
## <a name="net-framework-version-1-profiling-functions"></a>.NET Framework функции профилирования версии 1  
 [Функция FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Уведомляет профилировщик о передаче управления в функцию. Не рекомендуется использовать в .NET Framework 2,0.  
  
 [Функция FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту. Не рекомендуется использовать в .NET Framework 2,0.  
  
 [Функция FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail. Не рекомендуется использовать в .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Функции профилирования .NET Framework версии 2  
 [Функция FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в обратных вызовах [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) для этой функции. Также позволяет профилировщику указать, требуется ли получать обратные вызовы для этой функции.  
  
 [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Уведомляет профилировщик о передаче управления в функцию и предоставляет сведения о кадре стека и аргументах функции. Не рекомендуется использовать в .NET Framework 4.  
  
 [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Уведомляет профилировщик о том, что функция собирается вернуться к вызывающему объекту, и предоставляет сведения о кадре стека и возвращаемом значении функции. Не рекомендуется использовать в .NET Framework 4.  
  
 [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail и предоставляет сведения о кадре стека. Не рекомендуется использовать в .NET Framework 4.  
  
 [Функция StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Предоставляет профилировщику сведения о каждом управляемом кадре и каждом запуске неуправляемых кадров в стеке во время прохода стека, который инициируется методом [ICorProfilerInfo2::D остаккснапшот](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="net-framework-version-4-profiling-functions"></a>Функции профилирования .NET Framework версии 4  
 [Функция FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в ответных вызовах [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)или[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) для этой функции. Также позволяет профилировщику указывать, хотят ли они получать обратные вызовы для этой функции.  
  
 `FunctionIDMapper2` расширяет функцию [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) с помощью параметра `clientData`, который профилировщики могут использовать для устранения неоднозначности между средами выполнения.  
  
 [Функция FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Уведомляет профилировщик о передаче управления в функцию.  
  
 [Функция FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Уведомляет профилировщик о передаче управления в функцию и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) для получения кадра стека и аргументов функции.  
  
 [Функция FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Уведомляет профилировщик о том, что управление возвращается из функции.  
  
 [Функция FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Уведомляет профилировщик о том, что управление возвращается из функции, и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для получения кадра стека и возвращаемого значения.  
  
 [Функция FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.  
  
 [Функция FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail, и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для получения кадра стека.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о профилировании](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
