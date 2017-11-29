---
title: "Метод IHostMemoryManager::NeedsVirtualAddressSpace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.NeedsVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62ceb9e5b4d5843b8e2adad344b3ffb662ab3aff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a>Метод IHostMemoryManager::NeedsVirtualAddressSpace
Уведомляет основное приложение, общеязыковой среды выполнения (CLR) будет пытаться использовать указанный объем памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `startAddress`  
 [in] Начальный адрес памяти.  
  
 `size`  
 [in] Размер в байтах в памяти.  
  
## <a name="remarks"></a>Примечания  
 `NeedsVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы разработчиком ведущего приложения. Он вызывается средой CLR.  
  
 Если узел не требуется среда CLR для использования указанного объема памяти, может вернуть значение E_OUTOFMEMORY HRESULT.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IHostMemoryManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
