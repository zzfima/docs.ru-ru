---
title: "Структуры отладки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a>Структуры отладки
В этом разделе описаны неуправляемые структуры, которые использует API отладки.  
  
## <a name="in-this-section"></a>Содержание  
 [Clr_debugging_version-структура](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 Определяет версию продукта среды CLR, предназначенную для отладки.  
  
 [CodeChunkInfo Structure1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
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
  
 [Stacktrace_simplecontext-структура](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компонентные классы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
