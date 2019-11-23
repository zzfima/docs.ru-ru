---
title: 'ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионстартед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136466"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионстартед
[Поддерживается в .NET Framework 4,7 и более поздних версиях]  
  
Уведомляет профилировщик каждый раз, когда запускается JIT-компиляция динамического метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a>Параметры  
[входной] `functionId`  
Идентификатор функции в памяти, для которой запускается JIT-компиляция.   

[in] `fIsSafeToBlock`   
`true`, чтобы указать, что блокировка может привести к ожиданию средой выполнения вызывающего потока от этого обратного вызова. `false`, чтобы указать, что блокировка не повлияет на работу среды выполнения.  

[in] `pILHeader`    
Указатель на первый байт заголовка IL метода.   

[in] `cbILHeader`    
Число байтов в заголовке IL. 

## <a name="remarks"></a>Примечания  

Этот обратный вызов активируется всякий раз, когда динамический метод компилируется JIT-компилятором. Сюда входят различные суррогаты IL и методы LCG. Его цель — предоставить средствам записи профилировщика достаточно информации для распознавания скомпилированного метода для пользователей.

> [!NOTE]
> `functionId` значения нельзя использовать для разрешения их маркеров метаданных, так как динамические методы не имеют метаданных.

Указатель `pILHeader` допустим только во время обратного вызова.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback8-interface.md)
