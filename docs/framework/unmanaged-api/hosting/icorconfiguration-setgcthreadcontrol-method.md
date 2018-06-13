---
title: Метод ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9da3c0ee081b81411d13dfcf9c8557c6bd4d3448
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437311"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>Метод ICorConfiguration::SetGCThreadControl
Задает интерфейс обратного вызова для планирования потоков без выполнения задач, которые в противном случае были бы заблокированы для сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pGCThreadControl`  
 [in] Указатель на [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) объект, который уведомляет основное приложение о приостановки потоков для задач, отличных от среды выполнения.  
  
## <a name="remarks"></a>Примечания  
 Выбрать узел в [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) обратного вызова необходимость повторного планирования в потоке.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
