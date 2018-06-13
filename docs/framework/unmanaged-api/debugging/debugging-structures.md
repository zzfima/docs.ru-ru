---
title: Структуры отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c7415920d34fc231bf82dd00199c7e01eec7a73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408116"
---
# <a name="debugging-structures"></a>Структуры отладки
В этом разделе описаны неуправляемые структуры, которые использует API отладки.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Структура CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 Определяет версию продукта среды CLR, предназначенную для отладки.  
  
 [Структура1 CodeChunkInfo](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 Представляет одинарный блок кода в памяти.  
  
 [Структура CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 Определяет объект, блокирующий поток, и причину блокировки потока.  
  
 [Структура CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 Представляет предложение обработки исключений для данного фрагмента кода промежуточного языка.  
  
 [Структура CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 Представляет сведения о кадре стека из объекта исключения.  
  
 [Структура CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] с соответствующим [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) объекта.  
  
 COR_ACTIVE_FUNCTION  
 Содержит сведения о функциях, которые в данный момент активны в кадрах потока.  
  
 [Структура COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 Предоставляет сведения о расположении объекта массива в памяти.  
  
 COR_DEBUG_IL_TO_NATIVE_MAP  
 Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.  
  
 COR_DEBUG_STEP_RANGE  
 Содержит сведения о смещении для диапазона кода.  
  
 [Структура COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 Предоставляет сведения о поле в объекте.  
  
 [Структура COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.  
  
 [Структура COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.  
  
 [Структура COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 Предоставляет сведения об объекте, находящемся в управляемой куче.  
  
 COR_IL_MAP  
 Указывает изменения в относительном смещении функции.  
  
 [Структура COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 Содержит сведения об области памяти в управляемой куче.  
  
 [Структура COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 Содержит идентификатор типа.  
  
 [Структура COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 Предоставляет сведения о расположении объекта в памяти.  
  
 COR_VERSION  
 Содержит стандартный номер версии среды CLR, состоящий из четырех частей.  
  
 [Структура StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Коклассы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
