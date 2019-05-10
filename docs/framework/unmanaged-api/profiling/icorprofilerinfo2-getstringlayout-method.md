---
title: Метод ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a3d26a99844d00609b28eaef08ff0874a6701fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664963"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Метод ICorProfilerInfo2::GetStringLayout
Получает сведения о структуре строкового объекта. Этот метод является устаревшим в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]и заменяется [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBufferLengthOffset`  
 [out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки. Длина хранится в виде `DWORD`.  
  
> [!NOTE]
>  Этот параметр Возвращает длину самой строки, а не длину буфера. Длина буфера больше недоступен.  
  
 `PStringLengthOffset`  
 [out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки, сам. Длина хранится в виде `DWORD`.  
  
 `pBufferOffset`  
 [out] Указатель на смещение буфера, относительно `ObjectID` указатель, в котором хранится строка расширенных символов.  
  
## <a name="remarks"></a>Примечания  
 `GetStringLayout` Метод получает смещения, относительно `ObjectID` указатель из расположений, в которых хранятся следующие:  
  
- Длина буфера строки.  
  
- Длина самой строки.  
  
- Буфер, содержащий фактический строку расширенных символов.  
  
 Строки могут представлять собой нулем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
