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
ms.openlocfilehash: d30384ea8b9ff4eee41abd43ae39486f770039e7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041426"
---
# <a name="getcorsystemdirectory-function"></a>Функция GetCORSystemDirectory
Возвращает каталог установки среды CLR, который загружается в процесс. Каталог установки полностью квалифицирован, например "c:\windows\microsoft.net\framework\v1.0.3705".  
  
 Эта функция является устаревшей. Он заменяется методом [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) , предоставленным в .NET Framework 4.  
  
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
 заполняет Буфер, в котором среда выполнения возвращает строку, содержащую полное имя каталога установки для среды выполнения, которая загружается в процесс. Если среда выполнения еще не загружена в процесс, функция возвращает соответствующие сведения о каталоге для последней версии среды выполнения, установленной на компьютере.  
  
 `cchBuffer`  
 окне Размер (в байтах `pbuffer`).  
  
 `dwLength`  
 заполняет Число символов, возвращаемых в `pbuffer`.  
  
## <a name="remarks"></a>Примечания  
  
> [!CAUTION]
> Не используйте эту функцию в процессах, работающих в среде CLR версии 4. Если на компьютере установлена более ранняя версия среды CLR, эта функция возвращает каталог установки для этой версии.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
