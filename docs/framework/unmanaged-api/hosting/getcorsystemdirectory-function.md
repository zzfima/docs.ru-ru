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
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178207"
---
# <a name="getcorsystemdirectory-function"></a>Функция GetCORSystemDirectory
Возвращает каталог установки общего времени выполнения языка (CLR), который загружается в процесс. Каталог установки полностью квалифицирован, например, "c: »окна »microsoft.net» framework-v1.0.3705.  
  
 Эта функция является устаревшей. Он заменяется методом [ICLRRuntimeInfo::GetRuntimeDirectory,](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) представленным в системе .NET 4.  
  
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
 (ваут) Буфер, в котором время выполнения возвращает строку, содержащую полностью квалифицированное название каталога установки для времени выполнения, загруженного в процесс. Если время выполнения еще не загружено в процесс, функция возвращает соответствующую информацию каталога для последней версии времени выполнения, установленной на компьютере.  
  
 `cchBuffer`  
 (в) Размер, в байтах, из `pbuffer`.  
  
 `dwLength`  
 (ваут) Количество символов, возвращенных в `pbuffer`.  
  
## <a name="remarks"></a>Remarks  
  
> [!CAUTION]
> Не используйте эту функцию в процессах, которые работают версия 4 CLR. Если более ранняя версия CLR установлена на компьютере, эта функция возвращает каталог установки для этой версии.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
