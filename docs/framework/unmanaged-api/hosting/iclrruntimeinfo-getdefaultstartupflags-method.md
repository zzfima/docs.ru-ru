---
title: Метод ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 546a26306a1faaeceb1337b79bd2d27970d9f5be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434217"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>Метод ICLRRuntimeInfo::GetDefaultStartupFlags
Получает флаги загрузки и файл конфигурации главного узла, который будет использоваться для запуска среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pdwStartupFlags`  
 [out] Указатель флаги запуска узлов, заданных в настоящее время.  
  
 `pwzHostConfigFile`  
 [out] Указатель на путь к каталогу файла конфигурации текущего узла.  
  
 `pcchHostConfigFile`  
 [in, out] На входе, размер `pwzHostConfigFile`, чтобы избежать переполнения буфера. Если `pwzHostConfigFile` имеет значение null, метод возвращает требуемый размер `pwzHostConfigFile` для предварительного выделения памяти.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующий заданный HRESULT а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод возвращает значения по умолчанию флаг (`STARTUP_CONCURRENT_GC` и `NULL`), или значения, предоставленные предыдущего вызова [ICLRRuntimeInfo::setdefaultstartupflags-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), или значения, заданные с помощью любого из `CorBind*` методы, если они были привязаны к данной среды выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
