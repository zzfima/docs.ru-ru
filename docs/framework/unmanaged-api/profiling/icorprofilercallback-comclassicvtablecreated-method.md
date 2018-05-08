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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dcb45fcc987952ec5e84cc468dda8d8ede38bdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a>Метод ICorProfilerCallback::COMClassicVTableCreated
Уведомляет профилировщик, что виртуальной таблицы взаимодействия COM для заданного IID и класса был создан.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wrappedClasId`  
 [in] Идентификатор класса, для которого создан виртуальной таблице.  
  
 `implementedIID`  
 [in] Идентификатор интерфейса, реализуемого классом. Это значение может быть NULL, если интерфейс является только внутренним.  
  
 `pVTable`  
 [in] Указатель на начало таблицы vtable.  
  
 `cSlots`  
 [in] Число слотов, которые находятся в таблице vtable.  
  
## <a name="remarks"></a>Примечания  
 Профилировщик не должен блокироваться при реализации этого метода, так как стек может находиться в состоянии, допускающем сборку мусора, и поэтому не удастся включить сборку мусора. Если здесь профилировщик блокируется и выполняется сборка мусора, среда выполнения будет блокироваться до возвращает этот обратный вызов.  
  
 Реализация этого метода профилировщика не должны вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Метод COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
