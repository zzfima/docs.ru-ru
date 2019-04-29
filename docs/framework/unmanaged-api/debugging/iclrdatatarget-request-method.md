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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9005dd8fde0d7258bd1dd48b561e4925e87733b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698074"
---
# <a name="iclrdatatargetrequest-method"></a>Метод ICLRDataTarget::Request
Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определено в реализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 [in] Определяемые пользователем.  
  
 `inBufferSize`  
 [in] Размер входного буфера, который используется для входящего запроса.  
  
 `inBuffer`  
 [in] Буфер, содержащий запрос.  
  
 `outBufferSize`  
 [in] Размер выходного буфера, который используется для ответа.  
  
 `outBuffer`  
 [out] Буфер, содержащий ответ.  
  
## <a name="remarks"></a>Примечания  
 `Request` Метод облегчает процесс добавления неуказанных пользовательских операций. То есть этот метод обеспечивает расширяемость без необходимости версии определения интерфейса.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
