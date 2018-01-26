---
title: "Метод ICorProfilerInfo3::GetRuntimeInformation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetRuntimeInformation Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eadd9970d29cc65d8411692407dcae5471e51c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>Метод ICorProfilerInfo3::GetRuntimeInformation
Предоставляет сведения о среде (CLR) профилируемым версии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pClrInstanceId`  
 [out] Представителю идентификатор запущенного экземпляра среды CLR в процессе. Это то же самое, как `ClrInstanceID` , события трассировки событий Windows (ETW) при запуске отчетов.  
  
 `pRuntimeType`  
 [out] Тип среды выполнения. Этот параметр возвращает `COR_PRF_DESKTOP_CLR` для рабочего стола версии среды CLR, или `COR_PRF_CORE_CLR` для основной версии среды CLR, который используется в Silverlight.  
  
 `pMajorVersion`  
 [out] Основной номер версии среды CLR.  
  
 `pMinorVersion`  
 [out] Дополнительный номер версии среды CLR.  
  
 `pBuildVersion`  
 [out] Номер версии сборки среды CLR.  
  
 `pQFEVersion`  
 [out] Номер версии среды CLR, который связан с обновлением программного обеспечения.  
  
 `cchVersionString`  
 [in] Длина в символах, буфера, `szVersionString` указывает.  
  
 `pcchVersionString`  
 [out] Длина в символах для `szVersionString`.  
  
 `szVersionString`  
 [out] Строка версии CLR.  
  
## <a name="remarks"></a>Примечания  
 Можно передать значение null для любого параметра. Тем не менее `pcchVersionString` не может иметь значение null, если не `szVersionString` также имеет значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
