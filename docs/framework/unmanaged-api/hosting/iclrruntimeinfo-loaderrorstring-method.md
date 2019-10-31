---
title: Метод ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: 20f2041599e85b8df20a7a9cf44680da9f17244e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195931"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>Метод ICLRRuntimeInfo::LoadErrorString
Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 Этот метод заменяет следующие функции:  
  
- [лоадстрингрк](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [лоадстрингрцекс](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a>Параметры  
 `iResourceID`  
 окне Значение HRESULT для преобразования.  
  
 `pwzBuffer`  
 заполняет Строка сообщения, связанная с данным значением HRESULT.  
  
 `pcchBuffer`  
 [вход, выход] Размер `pwzbuffer`, чтобы избежать переполнения буфера. Если `pwzbuffer` имеет значение null, `pcchBuffer` предоставляет ожидаемый размер `pwzbuffer`, чтобы разрешить предварительное выделение.  
  
 `iLocaleID`  
 окне Идентификатор языка и региональных параметров. Чтобы использовать язык и региональные параметры по умолчанию, необходимо указать значение-1.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pcchBuffer` имеет значение null.|  
|E_INVALIDARG|Параметр `pwzBuffer` имеет значение null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
