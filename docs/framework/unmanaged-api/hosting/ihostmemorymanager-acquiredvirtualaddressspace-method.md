---
title: Метод IHostMemoryManager::AcquiredVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 423fbfc2bda9d3544a5c32b6cd650643209f0e86
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767242"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>Метод IHostMemoryManager::AcquiredVirtualAddressSpace
Уведомляет основное приложение, что общеязыковая среда выполнения (CLR) получила указанную память от операционной системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `startAddress`  
 [in] Начальный адрес памяти.  
  
 `size`  
 [in] Размер в байтах объем памяти.  
  
## <a name="remarks"></a>Примечания  
 `AcquiredVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы модулем записи ведущего приложения. Он вызывается средой CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
