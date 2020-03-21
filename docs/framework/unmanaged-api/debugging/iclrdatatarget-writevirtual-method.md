---
title: Метод ICLRDataTarget::WriteVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: bd2f67c2d7230d3873b4dc0df73ac1be778a0828
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179099"
---
# <a name="iclrdatatargetwritevirtual-method"></a>Метод ICLRDataTarget::WriteVirtual
Записывает данные из указанного буфера в указанный виртуальный адрес памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 (в) CLRDATA_ADDRESS, которая хранит виртуальный адрес памяти.  
  
 `buffer`  
 (в) Указатель на буфер, в течение которого хранятся данные, которые должны быть записаны.  
  
 `bytesRequested`  
 (в) Количество байтов, которые должны быть написаны.  
  
 `bytesWritten`  
 (ваут) Указатель на фактическое количество байтов, которые были написаны.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
