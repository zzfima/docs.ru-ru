---
title: Метод ICorProfilerCallback::COMClassicVTableCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
ms.openlocfilehash: 79be2572f52ec509d9551261074204bf62ad5388
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445062"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a>Метод ICorProfilerCallback::COMClassicVTableCreated
Уведомляет профилировщик о том, что для указанного IID и класса был создан объект vtable COM-взаимодействия.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a>Параметры  
 `wrappedClasId`  
 окне Идентификатор класса, для которого была создана таблица vtable.  
  
 `implementedIID`  
 окне Идентификатор интерфейса, реализуемого классом. Это значение может быть равно NULL, если интерфейс является только внутренним.  
  
 `pVTable`  
 окне Указатель на начало таблицы vtable.  
  
 `cSlots`  
 окне Число слотов в таблице vtable.  
  
## <a name="remarks"></a>Заметки  
 Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора. Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.  
  
 Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
