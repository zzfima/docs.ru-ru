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
ms.openlocfilehash: 64527221e81569bf08a3cfd34a66681725755a55
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490541"
---
# <a name="corlaunchapplication-function"></a>Функция CorLaunchApplication
Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
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
