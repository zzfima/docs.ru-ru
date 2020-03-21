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
ms.openlocfilehash: f3b51c1b376fa9c664de53aa76ec724ca305ae6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178181"
---
# <a name="getfileversion-function"></a>Функция GetFileVersion
Получает информацию о версии общего времени выполнения языка (CLR) указанного файла с использованием указанного буфера.  
  
 Эта функция была унесена в системе .NET 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFilename`  
 (в) Путь изучения файла.  
  
 `szBuffer`  
 (в, вне) Буфер, выделенный для возвращенной информации версии.  
  
 `cchBuffer`  
 (в) Размер, в широких символов, из `szBuffer`.  
  
 `dwLength`  
 (ваут) Размер, в байтах, `szBuffer`возвращенного .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
