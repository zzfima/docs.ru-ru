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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179117"
---
# <a name="iclrdatatargetrequest-method"></a>Метод ICLRDataTarget::Request
Вызывается службами общего времени выполнения языка (CLR) для запроса операции, как это определено в реализации.  
  
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
 (в) Определяется пользователями.  
  
 `inBufferSize`  
 (в) Размер буфера ввода, который используется для входящего запроса.  
  
 `inBuffer`  
 (в) Буфер, содержащий запрос.  
  
 `outBufferSize`  
 (в) Размер буфера вывода, который используется для ответа.  
  
 `outBuffer`  
 (ваут) Буфер, содержащий ответ.  
  
## <a name="remarks"></a>Remarks  
 Метод `Request` облегчает добавление неопределенных пользовательских операций. То есть этот метод обеспечивает расширяемость, не требуя пересмотра определения интерфейса.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
