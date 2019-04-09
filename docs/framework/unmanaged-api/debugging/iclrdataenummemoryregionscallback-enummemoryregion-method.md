---
title: Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85b1c5455cb2008a352461d6b506e43fcef48d17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130927"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
Вызывается средой [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) для сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 [in] Начальный адрес области памяти, которые необходимо перечислить.  
  
 `size`  
 [in] Размер в байтах, выделяемой области памяти.  
  
## <a name="remarks"></a>Примечания  
 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Метод будет вызывать этот метод обратного вызова после каждой попытки перечисления области памяти. Перечисление продолжится, даже если этот метод возвращает значение HRESULT, указывающее на сбой.  
  
 Регионы, о которых сообщает этот обратный вызов может быть дубликаты и перекрывающиеся области.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
