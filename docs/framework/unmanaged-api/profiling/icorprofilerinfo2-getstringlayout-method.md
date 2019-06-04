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
ms.openlocfilehash: faa5ecf63ac3795a58369d94f9fb15f853edb576
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490713"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Метод ICorProfilerInfo2::GetStringLayout
Получает сведения о структуре строкового объекта. Этот метод является устаревшим в .NET Framework 4 и заменяется [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) метод.  
  
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
