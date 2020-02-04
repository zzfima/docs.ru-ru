---
title: Метод ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: a6b36883ec0914426b4f4c937390c1622faead25
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868295"
---
# <a name="icorprofilermoduleenumclone-method"></a>Метод ICorProfilerModuleEnum::Clone
Получает указатель интерфейса на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) . Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя. Однако начальная позиции курсора копии совпадает с текущей позицией курсора этого перечислителя.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
