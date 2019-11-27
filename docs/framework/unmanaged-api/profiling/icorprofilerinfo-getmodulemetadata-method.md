---
title: Метод ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: c7bf8e3ebedb17a4536b604909434c3e004fc828
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439826"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Метод ICorProfilerInfo::GetModuleMetaData
Возвращает экземпляр интерфейса метаданных, сопоставляемый с указанным модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор модуля, с которым будет сопоставлен экземпляр интерфейса.  
  
 `dwOpenFlags`  
 окне Значение перечисления [коропенфлагс](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) , указывающее режим открытия файлов манифеста. Допустимы только `ofRead`, `ofWrite` и `ofNoTransform` разрядов.  
  
 `riid`  
 окне Идентификатор ссылки (GUID) интерфейса метаданных, экземпляр которого будет извлечен. Список интерфейсов см. в разделе [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) .  
  
 `ppOut`  
 заполняет Указатель на адрес экземпляра интерфейса метаданных.  
  
## <a name="remarks"></a>Примечания  
 Можно запросить открытие метаданных в режиме чтения/записи, но это приведет к более медленному выполнению метаданных программы, так как изменения метаданных не могут быть оптимизированы по мере их постановки в компилятор.  
  
 Некоторые модули (например, модули ресурсов) не имеют метаданных. В таких случаях `GetModuleMetaData` возвратит значение HRESULT S_FALSE и значение NULL в *`ppOut`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
