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
ms.openlocfilehash: e01698d2d8491b2496bb664c13dca97964cd1481
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136949"
---
# <a name="corlaunchapplication-function"></a>Функция CorLaunchApplication
Запускает приложение по указанному сетевому пути, используя указанные манифесты и другие данные приложения.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
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
 окне Значение перечисления [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) , указывающее тип узла, запускающего приложение.  
  
 `pwzAppFullName`  
 окне Полное имя запускаемого приложения.  
  
 `dwManifestPaths`  
 окне Число путей манифеста для приложения.  
  
 `ppwzManifestPaths`  
 окне Массив строк, каждый из которых указывает путь к манифесту запускаемого приложения.  
  
 `dwActivationData`  
 окне Количество элементов данных активации для запускаемого приложения.  
  
 `ppwzActivationData`  
 окне Массив строк, каждый из которых является элементом данных активации для запускаемого приложения.  
  
 `lpProcessInformation`  
 заполняет Указатель на сведения о процессе, в котором было загружено приложение.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
