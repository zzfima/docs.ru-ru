---
title: "Метод ICLRRuntimeInfo::GetInterface"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0049b4e60f803fbc9ec64e7f20273b1d5729e67f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetinterface-method"></a>Метод ICLRRuntimeInfo::GetInterface
Загружает среду CLR в текущий процесс и возвращает среды выполнения указателей интерфейса, такие как [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), и [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).  
  
 Этот метод заменяет все `CorBindTo`* функции в [устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) раздела.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a>Параметры  
 `rclsid`  
 [in] Интерфейс CLSID для компонентного класса.  
  
 `riid`  
 [in] Идентификатор IID запрошенного `rclsid` интерфейса.  
  
 `ppUnk`  
 [out] Указатель на запрашиваемый интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `ppUnk` имеет значение NULL.|  
|E_OUTOFMEMORY|Недостаточно памяти для обработки запроса.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Другая среда выполнения уже была привязана к прежних версий среды CLR политике активации версии 2.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод вызывает средой CLR с целью загружено, но не инициализирован.  
  
 В следующей таблице показаны поддерживаемые сочетания для `rclsid` и `riid`.  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|CLSID_CorMetaDataDispenser|IID_IMetaDataDispenser IID_IMetaDataDispenserEx|  
|CLSID_CorMetaDataDispenserRuntime|IID_IMetaDataDispenser IID_IMetaDataDispenserEx|  
|CLSID_CorRuntimeHost|IID_ICorRuntimeHost|  
|CLSID_CLRRuntimeHost|IID_ICLRRuntimeHost|  
|CLSID_TypeNameFactory|IID_ITypeNameFactory|  
|CLSID_CLRDebuggingLegacy|IID_ICorDebug|  
|||  
|CLSID_CLRStrongName|IID_ICLRStrongName|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRRuntimeInfo-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
