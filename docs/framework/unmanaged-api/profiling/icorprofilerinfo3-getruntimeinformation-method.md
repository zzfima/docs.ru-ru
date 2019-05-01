---
title: Метод ICorProfilerInfo3::GetRuntimeInformation
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a13e3e525c7f019e7dc49111b88ac374345830af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000601"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>Метод ICorProfilerInfo3::GetRuntimeInformation
Предоставляет сведения о среда CLR (CLR) профилируемым версии.  
  
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
  
## <a name="parameters"></a>Параметры  
 `pClrInstanceId`  
 [out] Идентификатор представителем работающего экземпляра среды CLR в процессе. Так же, как это `ClrInstanceID` сообщает, трассировка событий для события при запуске Windows (ETW).  
  
 `pRuntimeType`  
 [out] Тип среды выполнения. Этот параметр возвращает `COR_PRF_DESKTOP_CLR` для настольной версии среды CLR, или `COR_PRF_CORE_CLR` для основную версию среды CLR, используемую в Silverlight.  
  
 `pMajorVersion`  
 [out] Основной номер версии среды CLR.  
  
 `pMinorVersion`  
 [out] Дополнительный номер версии среды CLR.  
  
 `pBuildVersion`  
 [out] Номер версии сборки среды CLR.  
  
 `pQFEVersion`  
 [out] Номер версии среды CLR, связанный с обновлением программного обеспечения.  
  
 `cchVersionString`  
 [in] Длина в символах, буфера, `szVersionString` указывает.  
  
 `pcchVersionString`  
 [out] Длина в символах, из `szVersionString`.  
  
 `szVersionString`  
 [out] Строка версии среды CLR.  
  
## <a name="remarks"></a>Примечания  
 Можно передать значение null для любого параметра. Тем не менее `pcchVersionString` не может иметь значение null Если `szVersionString` также имеет значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
