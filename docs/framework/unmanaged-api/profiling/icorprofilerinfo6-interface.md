---
title: Интерфейс ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041123"
---
# <a name="icorprofilerinfo6-interface"></a>Интерфейс ICorProfilerInfo6
[Поддерживается в .NET Framework 4.6 и более поздних версиях]  
  
 Подкласс [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) , предоставляющий перечислитель для всех методов, которые определены в указанный модуль NGen и в строке данного метода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Возвращает перечислитель для всех методов, которые принадлежат данного модуля NGen и, встраиваются в тексте данного метода.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
