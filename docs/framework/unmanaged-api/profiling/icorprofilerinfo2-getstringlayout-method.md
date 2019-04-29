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
ms.openlocfilehash: cc94c63edb602d87a7c08a9051eb2ef760834477
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791681"
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
