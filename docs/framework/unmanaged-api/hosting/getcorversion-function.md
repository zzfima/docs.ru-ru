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
ms.openlocfilehash: d0e922273a7d4e5b98c1321992e5e89e01adb437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431497"
---
# <a name="getcorversion-function"></a>Функция GetCORVersion
Возвращает номер версии среды common language runtime (CLR), на котором выполняется в текущем процессе.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `pbuffer`  
 Указатель на буфер, в котором среда CLR возвращает строку, задающую версию среды выполнения, загруженные в процесс. Возвращаемая строка принимает ту же форму, как строки, переданной в [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), например, «v1.0.1216». Если среда выполнения еще не был загружен в процесс, функция возвращает сведения каталога, соответствующего последнюю версию среды выполнения, установленную на компьютере.  
  
 `cchBuffer`  
 Число символов (`WCHAR`s) может содержаться в `pbuffer`.  
  
 `dwLength`  
 Указатель на число символов, фактически извлеченных в `pbuffer`. Если `pbuffer` является пустым указателем, среда выполнения возвращает E_POINTER. Если количество знаков больше длины `pbuffer` , среда выполнения возвращает ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
