---
title: Метод ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a3c1aad3bcd6151267671122fb21772082e15cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658784"
---
# <a name="iclrdatatargetsettlsvalue-method"></a>Метод ICLRDataTarget::SetTLSValue
Задает значение в локальном хранилище потока (TLS) заданного потока в целевом процессе. Этот метод вызывается службами доступа к данным среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока в целевом процессе операционной системы.  
  
 `index`  
 [in] Индекс расположения. Это значение должно быть допустимым индексом в локальном хранилище из указанного потока.  
  
 `value`  
 [in] Объект `CLRDATA_ADDRESS` значение, указывающее значение, помещаемое в заданном расположении TLS.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
