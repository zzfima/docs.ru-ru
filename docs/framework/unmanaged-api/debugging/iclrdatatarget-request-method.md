---
title: Метод ICLRDataTarget::Request
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: e5d7a6b9826a734363d6beeb2e3fab8422964558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113353"
---
# <a name="iclrdatatargetrequest-method"></a>Метод ICLRDataTarget::Request
Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `reqCode`  
 окне Определяется пользователем.  
  
 `inBufferSize`  
 окне Размер входного буфера, используемого для входящего запроса.  
  
 `inBuffer`  
 окне Буфер, содержащий запрос.  
  
 `outBufferSize`  
 окне Размер выходного буфера, используемого для ответа.  
  
 `outBuffer`  
 заполняет Буфер, содержащий ответ.  
  
## <a name="remarks"></a>Заметки  
 Метод `Request` упрощает добавление неуказанных пользовательских операций. Это значит, что этот метод обеспечивает расширяемость без необходимости пересмотра определения интерфейса.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
