---
title: Метод ICLRDataTarget3::GetExceptionThreadID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de3606e4763596038a2c573002d774c6348071e8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473517"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>Метод ICLRDataTarget3::GetExceptionThreadID
Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 [из] Идентификатор потока, вызвавшего исключение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Коды `HRESULT` могут включать значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Не удалось найти допустимый идентификатор потока для исключения.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [Метод GetExceptionContextRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [Метод GetExceptionRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
