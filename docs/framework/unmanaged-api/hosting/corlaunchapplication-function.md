---
title: Функция CorLaunchApplication
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e10a92b1748fcdf518fa68cb7054731f4511396b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487191"
---
# <a name="corlaunchapplication-function"></a>Функция CorLaunchApplication
Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
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
  
## <a name="parameters"></a>Параметры  
 `dwClickOnceHost`  
 [in] Значение [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) перечисление, указывающее тип узла, которое запускает приложение.  
  
 `pwzAppFullName`  
 [in] Полное имя приложения, запускаемый.  
  
 `dwManifestPaths`  
 [in] Количество путей манифестов для приложения.  
  
 `ppwzManifestPaths`  
 [in] Массив строк, каждый из которых указывает путь к манифесту приложения, запускаемый.  
  
 `dwActivationData`  
 [in] Число элементов данных активации для приложения, запускаемый.  
  
 `ppwzActivationData`  
 [in] Массив строк, каждый из которых представляет элемент данных активации для приложения, запускаемый.  
  
 `lpProcessInformation`  
 [out] Указатель на сведения о процессе, в котором было загружено приложение.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
