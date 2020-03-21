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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178194"
---
# <a name="getcorversion-function"></a>Функция GetCORVersion
Возвращает номер версии общего времени выполнения языка (CLR), который работает в текущем процессе.  
  
 Эта функция была унесена в системе .NET 4.  
  
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
 Указатель на буфер, в котором CLR возвращает строку с указанием версии времени выполнения, которая в настоящее время загружается в процесс. Возвращалась строка принимает ту же форму, что и строки, передаваемые [CorBindToRuntimeEx,](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)например, "v1.0.1216". Если время выполнения еще не загружено в процесс, функция возвращает соответствующую информацию каталога для последней версии времени выполнения, установленной на компьютере.  
  
 `cchBuffer`  
 Количество символов (ы),`WCHAR`которые могут `pbuffer`быть проведены в .  
  
 `dwLength`  
 Указатель на количество символов на `pbuffer`самом деле вернулся в . Если `pbuffer` это нулевая указка, время выполнения возвращается E_POINTER. Если количество символов больше, то `pbuffer` длина, время выполнения возвращается ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
