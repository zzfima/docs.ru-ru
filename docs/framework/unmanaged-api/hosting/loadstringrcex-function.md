---
title: "Функция LoadStringRCEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b046387b5ae365ece694509b302f7ac3a7e066a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrcex-function"></a>Функция LoadStringRCEx
Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lcid`  
 [in] Идентификатор языка и региональных параметров. Передайте значение -1 `lcid` для использования с языком по умолчанию.  
  
 `iResourceID`  
 [in] Значение HRESULT.  
  
 `szBuffer`  
 [out] Буфер, содержащий сообщение об ошибке после успешного завершения.  
  
 `iMax`  
 [in] Размер буфера сообщений ошибок.  
  
 `bQuiet`  
 [in] Не обрабатывается.  
  
 `pcwchUsed`  
 [out] Указатель на длину сообщение об ошибке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.  
  
|Код возврата|Описание:|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`szBuffer`имеет значение null, или `iMax` равно нулю (0).|  
  
## <a name="remarks"></a>Примечания  
 Если метод завершается успешно, `szBuffer` содержит пустую строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [Функция LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
