---
title: "Функция GetRequestedRuntimeVersionForCLSID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be55754bc626ce24c51eec7b10d9f46aec92cfe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Функция GetRequestedRuntimeVersionForCLSID
Получает соответствующий общий среды выполнения (CLR) сведения о языке для класса с указанным `CLSID`.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
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
 [out]  Буфер, содержащий строку номера версии при успешном выполнении.  
  
 `cchBuffer`  
 [in]  Размер в расширенные символы из `pVersion` буфера.  
  
 `dwLength`  
 [out] Длина возвращаемого буфера в байтах.  
  
 `dwResolutionFlags`  
 [in]  Одно из значений CLSID_RESOLUTION_FLAGS. Поддерживаются следующие значения:  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) указывает взаимодействия поведение по умолчанию следует использовать.  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) указывает, что реестр следует выполнять поиск и создать оболочку политики должны быть применены.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Функция успешно возвращен.|  
|E_INVALIDARG|Один из параметров имеет недопустимый тип или формат.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion` Буфер недостаточно велик для хранения всю строку версии.|  
|REGDB_E_CLASSNOTREG|Нет зарегистрированных с помощью указанного класса `CLSID`.|  
|E_POINTER|`dwLength`имеет значение null, или `cchBuffer` достаточно велик для хранения строки версии, но `pVersion` имеет значение null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
