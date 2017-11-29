---
title: "Метод ICorProfilerInfo::GetModuleMetaData"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 540ed6f1f84f096563aa94798090c3511d6db5d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Метод ICorProfilerInfo::GetModuleMetaData
Получает экземпляр интерфейса метаданных, сопоставляемый с указанным модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, с которым сопоставлен экземпляр интерфейса.  
  
 `dwOpenFlags`  
 [in] Значение [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления, указывающее режим для открытия файлов манифеста. Только `ofRead`, `ofWrite` и `ofNoTransform` bits являются допустимыми.  
  
 `riid`  
 [in] Ссылка идентификатор (GUID) интерфейс метаданных, экземпляр которого будут извлечены. В разделе [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) список интерфейсов.  
  
 `ppOut`  
 [out] Указатель на адрес объекта интерфейса экземпляра метаданных.  
  
## <a name="remarks"></a>Примечания  
 Существует возможность запросить метаданные для открытия в режиме чтения и записи, но это приведет к замедлению выполнения программы, поскольку изменения метаданных не может быть оптимизирован, как компилятор.  
  
 Некоторые модули (например, модули ресурсов) имеют без метаданных. В таких случаях `GetModuleMetaData` возвратит значение HRESULT S_FALSE и null в *`ppOut`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
