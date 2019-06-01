---
title: Глобальные статические функции профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ea65c06871d9762fa6daac229a568594b4c4479
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457476"
---
# <a name="profiling-global-static-functions"></a>Глобальные статические функции профилирования
В этом разделе описываются неуправляемые функции API, которые использует API профилирования.  
  
## <a name="in-this-section"></a>В этом разделе  
  
## <a name="net-framework-version-1-profiling-functions"></a>Функции профилирования .NET framework версии 1  
 [Функция FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Уведомляет профилировщик, что элемент управления передается в функцию. Рекомендуется использовать в .NET Framework 2.0.  
  
 [Функция FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Уведомляет профилировщик, что функция должна возвращать вызывающей стороне. Рекомендуется использовать в .NET Framework 2.0.  
  
 [Функция FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию. Рекомендуется использовать в .NET Framework 2.0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Функции профилирования .NET framework версии 2  
 [Функция FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Уведомляет профилировщик о заданному идентификатору функции может быть альтернативный идентификатор для использования в [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) обратные вызовы для этой функции. Также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции  
  
 [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Уведомляет профилировщик о том, что элемент управления передается в функцию и предоставляет информацию о стеке кадра и аргументов функции. Рекомендуется использовать в .NET Framework 4.  
  
 [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Уведомляет профилировщик, что функция должна возвращать вызывающей стороне и предоставляет сведения о стека кадра и функция возвращаемое значение. Рекомендуется использовать в .NET Framework 4.  
  
 [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Уведомляет профилировщик, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию и предоставляет сведения о кадре стека. Рекомендуется использовать в .NET Framework 4.  
  
 [Функция StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Предоставляет сведения о каждого управляемого кадра и каждом запуске неуправляемых фреймов в стеке во время стека, который инициируется профилировщик [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Функции профилирования .NET framework версии 4  
 [Функция FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Уведомляет профилировщик о заданному идентификатору функции может быть альтернативный идентификатор для использования в [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), и [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), или[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), и [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) обратные вызовы для этой функции. также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.  
  
 `FunctionIDMapper2` расширяет [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) функционировать с `clientData` параметра, которого профилировщики могут различать среды выполнения.  
  
 [Функция FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Уведомляет профилировщик, что элемент управления передается в функцию.  
  
 [Функция FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Уведомляет профилировщик о том, что элемент управления передается в функцию и предоставляет маркер, который может быть передан [ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) для извлечения кадра стека и функция аргументов.  
  
 [Функция FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Уведомляет профилировщик, что элемент управления возвращается из функции.  
  
 [Функция FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Уведомляет профилировщик, что элемент управления возвращается из функции и предоставляет маркер, который может быть передан [ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для извлечения кадра стека и возвращаемое значение.  
  
 [Функция FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию.  
  
 [Функция FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Уведомляет профилировщик, текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию и предоставляет маркер, который может быть передан [ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для извлечения кадра стека.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о профилировании](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
