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
ms.openlocfilehash: 63ad2532240c9f18a00421281fae0d111dbfaec5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963796"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Метод ICorProfilerInfo2::GetStringLayout
Получает сведения о структуре строкового объекта. Этот метод является устаревшим в .NET Framework 4 и заменяется методом [ICorProfilerInfo3:: GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBufferLengthOffset`  
 заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки. Длина хранится в виде `DWORD`.  
  
> [!NOTE]
> Этот параметр возвращает длину самой строки, а не длину буфера. Длина буфера больше недоступна.  
  
 `PStringLengthOffset`  
 заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки. Длина хранится в виде `DWORD`.  
  
 `pBufferOffset`  
 заполняет Указатель на смещение буфера относительно `ObjectID` указателя, в котором хранится строка расширенных символов.  
  
## <a name="remarks"></a>Примечания  
 Метод получает смещения, относящиеся `ObjectID` к указателю, для расположений, в которых хранятся следующие значения: `GetStringLayout`  
  
- Длина буфера строки.  
  
- Длина самой строки.  
  
- Буфер, содержащий фактическую строку расширенных символов.  
  
 Строки могут завершаться нулем.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
