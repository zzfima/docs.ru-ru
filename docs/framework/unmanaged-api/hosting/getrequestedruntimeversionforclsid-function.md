---
title: Функция GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e00bc95dd9b54d5451da65cefbfff13395e467f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511966"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Функция GetRequestedRuntimeVersionForCLSID
Получает соответствующий информация среды CLR (CLR) версии для класса с указанным `CLSID`.  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `rclsid`  
 [in]  `CLSID` Компонента.  
  
 `pVersion`  
 [out]  Буфер, содержащий строку номера версии после успешного завершения.  
  
 `cchBuffer`  
 [in]  Размер в расширенные символы из `pVersion` буфера.  
  
 `dwLength`  
 [out] Длина в байтах, возвращенного буфера.  
  
 `dwResolutionFlags`  
 [in]  Одно из значений CLSID_RESOLUTION_FLAGS. Поддерживаются следующие значения:  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) указывает, что следует использовать взаимодействия по умолчанию.  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) указывает, следует ли выполнять поиск реестра и должна ли применяться политика оболочек совместимости.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Функция успешно возвращен.|  
|E_INVALIDARG|Один из параметров имеет недопустимый тип или формат.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion` Буфера недостаточен для хранения всей строки версии.|  
|REGDB_E_CLASSNOTREG|Отсутствует класс зарегистрирован с указанным `CLSID`.|  
|E_POINTER|`dwLength` имеет значение null, или `cchBuffer` достаточно велик для хранения строки версии, но `pVersion` имеет значение null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
