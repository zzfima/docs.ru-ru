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
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868620"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Метод ICorProfilerInfo2::GetStringLayout
Получает сведения о структуре строкового объекта. Этот метод является устаревшим в .NET Framework 4 и заменяется методом [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBufferLengthOffset`  
 заполняет Указатель на смещение расположения относительно указателя `ObjectID`, в котором хранится длина строки. Длина хранится в виде `DWORD`.  
  
> [!NOTE]
> Этот параметр возвращает длину самой строки, а не длину буфера. Длина буфера больше недоступна.  
  
 `PStringLengthOffset`  
 заполняет Указатель на смещение расположения относительно указателя `ObjectID`, в котором хранится длина строки. Длина хранится в виде `DWORD`.  
  
 `pBufferOffset`  
 заполняет Указатель на смещение буфера относительно указателя на `ObjectID`, в котором хранится строка расширенных символов.  
  
## <a name="remarks"></a>Заметки  
 Метод `GetStringLayout` получает смещения относительно указателя `ObjectID` в расположениях, в которых хранятся следующие значения:  
  
- Длина буфера строки.  
  
- Длина самой строки.  
  
- Буфер, содержащий фактическую строку расширенных символов.  
  
 Строки могут завершаться нулем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
