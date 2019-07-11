---
title: Функция GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deec4d40270a11b9e48a0ab39504d774314c077c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736186"
---
# <a name="getcorsystemdirectory-function"></a>Функция GetCORSystemDirectory
Возвращает каталог установки среда CLR (CLR), который загружается процесс. Каталог установки — полное имя, например, «c:\windows\microsoft.net\framework\v1.0.3705».  
  
 Эта функция является устаревшей. Он заменен [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) метода .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Параметры  
 `pbuffer`  
 [out] Буфер, в котором среда выполнения возвращает строку, содержащую полное имя каталога установки для среды выполнения, который загружается в процесс. Если среда выполнения еще не был загружен в процесс, функция возвращает данные каталога, соответствующего для последней версии среды выполнения, установленную на компьютере.  
  
 `cchBuffer`  
 [in] Размер в байтах из `pbuffer`.  
  
 `dwLength`  
 [out] Число символов, возвращаемых в `pbuffer`.  
  
## <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Не используйте эту функцию в процессах, работающих под управлением версии 4 среды CLR. Если на компьютере установлена более ранняя версия среды CLR, эта функция возвращает каталог установки этой версии.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
