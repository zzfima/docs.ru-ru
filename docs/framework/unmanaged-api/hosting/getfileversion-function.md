---
title: Функция GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf63b2641c4140b287a3932c2073b445211ad3aa
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490365"
---
# <a name="getfileversion-function"></a>Функция GetFileVersion
Получает информация среды CLR (CLR) версии указанного файла, используя указанный буфер.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFilename`  
 [in] Путь к файлу, который необходимо проверить.  
  
 `szBuffer`  
 [in, out] Буфер, выделенный для сведений о версии, который возвращается.  
  
 `cchBuffer`  
 [in] Размер в расширенные символы из `szBuffer`.  
  
 `dwLength`  
 [out] Размер в байтах, возвращаемого `szBuffer`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
