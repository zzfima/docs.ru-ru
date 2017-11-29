---
title: "Метод ICLRDataTarget::Request"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.Request
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e0ce905ea21267419e6a68e73f918de8fc364f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetrequest-method"></a>Метод ICLRDataTarget::Request
Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определяются реализацией.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `reqCode`  
 [in] Определяемые пользователем.  
  
 `inBufferSize`  
 [in] Размер входного буфера, который используется для входящего запроса.  
  
 `inBuffer`  
 [in] Буфер, содержащий запрос.  
  
 `outBufferSize`  
 [in] Размер выходного буфера, используемого для ответа.  
  
 `outBuffer`  
 [out] Буфер, содержащий ответ.  
  
## <a name="remarks"></a>Примечания  
 `Request` Метод облегчает процесс добавления незаданных настраиваемых операций. То есть этот метод обеспечивает расширяемость, не требуя пересмотра определения интерфейса.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRDataTarget-интерфейс](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
