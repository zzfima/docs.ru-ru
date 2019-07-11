---
title: Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 276a69deecccc91b3c511403c2bd0d5c0baabd9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772799"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a>Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException
Возвращает сегмент Watson для текущего исключения в вызывающем потоке.  
  
 Объект *контейнеров* — это коллекция данные об ошибках, которая связана с дефектом кода. *"Доктор Ватсон"* ссылается на набор технологий для сбора и анализа данных, связанный с исключением.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pParams`  
 [out] Указатель на [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) структуру, которая содержит данные об ошибках для исключения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
