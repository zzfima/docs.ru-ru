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
ms.openlocfilehash: a412bd8410750ec826762e45d70d59c514c61542
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490381"
---
# <a name="getcorsystemdirectory-function"></a>Функция GetCORSystemDirectory
Возвращает каталог установки среда CLR (CLR), который загружается процесс. Каталог установки — полное имя, например, «c:\windows\microsoft.net\framework\v1.0.3705».  
  
 Эта функция является устаревшей. Он заменен [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) метода .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
