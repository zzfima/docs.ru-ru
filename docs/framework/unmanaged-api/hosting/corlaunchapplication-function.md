---
title: "Функция CorLaunchApplication"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bf4392f7b30a5faa1cb01e24f9262260d9c6e93a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corlaunchapplication-function"></a>Функция CorLaunchApplication
Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwClickOnceHost`  
 [in] Значение [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) перечисление, указывающее тип узла, которое запускает приложение.  
  
 `pwzAppFullName`  
 [in] Полное имя запускаемое приложение.  
  
 `dwManifestPaths`  
 [in] Количество путей манифестов для приложения.  
  
 `ppwzManifestPaths`  
 [in] Массив строк, каждый из которых задает путь к манифесту приложения, которое запускается.  
  
 `dwActivationData`  
 [in] Число элементов данных активации для приложения, в которой запускается.  
  
 `ppwzActivationData`  
 [in] Массив строк, каждый из которых является активации элемента данных для приложения, в которой запускается.  
  
 `lpProcessInformation`  
 [out] Указатель на сведения о процессе, в котором был загружен приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
