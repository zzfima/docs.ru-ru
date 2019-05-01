---
title: Функция GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ee737f4c6d34e77996f5ba08ce4d84132a99238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985664"
---
# <a name="getrequestedruntimeversion-function"></a>Функция GetRequestedRuntimeVersion
Возвращает номер версии общеязыковой среды выполнения (CLR), запрашиваемой указанным приложением. Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрашиваемой.  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pExe`  
 [in] Имя приложения.  
  
 `pVersion`  
 [out] Буфер, содержащий строку номера версии после успешного завершения.  
  
 `cchBuffer`  
 [in] Длина буфера версии.  
  
 `pdwLength`  
 [out] Указатель на длину строку номера версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Версии буфера недостаточен для хранения строки версии.|  
|E_POINTER|Параметр `pdwLength` имеет значение null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
