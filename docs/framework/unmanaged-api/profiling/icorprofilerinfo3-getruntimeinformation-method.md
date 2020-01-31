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
ms.openlocfilehash: e3d167be9a4091ae57a3283424186142e90ca7a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868555"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>Метод ICorProfilerInfo3::GetRuntimeInformation
Предоставляет сведения о версии для профилирования среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 заполняет Репрезентативный идентификатор выполняющегося экземпляра среды CLR в процессе. Это то же самое, что `ClrInstanceID`, что отчеты о событиях запуска трассировки событий Windows (ETW).  
  
 `pRuntimeType`  
 заполняет Тип среды выполнения. Этот параметр возвращает `COR_PRF_DESKTOP_CLR` для классической версии среды CLR или `COR_PRF_CORE_CLR` для основной версии среды CLR, используемой в Silverlight.  
  
 `pMajorVersion`  
 заполняет Основной номер версии среды CLR.  
  
 `pMinorVersion`  
 заполняет Дополнительный номер версии среды CLR.  
  
 `pBuildVersion`  
 заполняет Номер версии сборки среды CLR.  
  
 `pQFEVersion`  
 заполняет Номер версии среды CLR, связанной с обновлением программного обеспечения.  
  
 `cchVersionString`  
 окне Длина (в символах) буфера, на который `szVersionString` указывает.  
  
 `pcchVersionString`  
 заполняет Длина `szVersionString`в символах.  
  
 `szVersionString`  
 заполняет Строка версии среды CLR.  
  
## <a name="remarks"></a>Заметки  
 Вы можете передать значение NULL для любого параметра. Однако `pcchVersionString` не может иметь значение null, если `szVersionString` также не имеет значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
