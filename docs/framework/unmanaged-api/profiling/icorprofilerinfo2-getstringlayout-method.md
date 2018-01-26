---
title: "Метод ICorProfilerInfo2::GetStringLayout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ad91829fab31b47a1dd51bb6cc9118c2ebe4c3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Параметры  
 `pBufferLengthOffset`  
 [out] Указатель на расположение относительно смещение `ObjectID` указатель, в которой хранится длина строки. Длина хранится в виде `DWORD`.  
  
> [!NOTE]
>  Этот параметр Возвращает длину самой строки, а не длину буфера. Длина буфера больше не доступен.  
  
 `PStringLengthOffset`  
 [out] Указатель на расположение относительно смещение `ObjectID` указатель, в которой хранится Длина самой строки. Длина хранится в виде `DWORD`.  
  
 `pBufferOffset`  
 [out] Указатель на смещение буфера относительно `ObjectID` указатель, который сохраняет строку расширенных символов.  
  
## <a name="remarks"></a>Примечания  
 `GetStringLayout` Метод получает смещения, относительно `ObjectID` указатель расположений, в которых хранятся следующие:  
  
-   Длина буфера строки.  
  
-   Длина самой строки.  
  
-   Буфер, содержащий фактический строку расширенных символов.  
  
 Строки могут заканчиваться символом null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
