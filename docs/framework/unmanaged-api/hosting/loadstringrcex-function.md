---
title: Функция LoadStringRCEx
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5520aef09c72819ff2b3763cd43af13f013263c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490211"
---
# <a name="loadstringrcex-function"></a>Функция LoadStringRCEx
Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
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
  
## <a name="parameters"></a>Параметры  
 `lcid`  
 [in] Идентификатор языка и региональных параметров. Передайте значение -1 `lcid` использовать культуры по умолчанию.  
  
 `iResourceID`  
 [in] Значение HRESULT.  
  
 `szBuffer`  
 [out] Буфер, который содержит сообщение об ошибке после успешного завершения.  
  
 `iMax`  
 [in] Размер буфера сообщений ошибок.  
  
 `bQuiet`  
 [in] Игнорируется.  
  
 `pcwchUsed`  
 [out] Указатель на длину сообщение об ошибке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, помимо следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`szBuffer` имеет значение null, или `iMax` равно нулю (0).|  
  
## <a name="remarks"></a>Примечания  
 Если метод завершается успешно, `szBuffer` содержит пустую строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [Функция LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
