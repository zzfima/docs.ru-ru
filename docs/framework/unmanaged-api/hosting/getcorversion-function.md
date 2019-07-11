---
title: Функция GetCORVersion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe5525fc29bc01bb84f7f2997d115eec12d72b13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736275"
---
# <a name="getcorversion-function"></a>Функция GetCORVersion
Возвращает номер версии среда CLR (CLR), на котором выполняется в текущем процессе.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Параметры  
 `pbuffer`  
 Указатель на буфер, в котором среда CLR возвращает строку, представляющую версию среды выполнения, который в данный момент загружается процесс. Возвращаемая строка принимает ту же форму, как строки, переданной в [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), например, «v1.0.1216». Если среда выполнения еще не был загружен в процесс, функция возвращает данные каталога, соответствующего для последней версии среды выполнения, установленную на компьютере.  
  
 `cchBuffer`  
 Число символов (`WCHAR`s), могут храниться в `pbuffer`.  
  
 `dwLength`  
 Указатель на число символов, фактически возвращенных в `pbuffer`. Если `pbuffer` является пустым указателем, среда выполнения возвращает E_POINTER. Если количество символов больше длины `pbuffer` , среда выполнения возвращает значение ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
