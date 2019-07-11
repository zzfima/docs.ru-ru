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
ms.openlocfilehash: 9861de733a9acb43c7e2a4b4941f9945fc5f0ba7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758375"
---
# <a name="corlaunchapplication-function"></a>Функция CorLaunchApplication
Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
