---
title: Функция GetVersionFromProcess
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178119"
---
# <a name="getversionfromprocess-function"></a>Функция GetVersionFromProcess
Получает номер версии общего времени выполнения языка (CLR), который связан с указанной ручкой процесса.  
  
 Эта функция была унесена в системе .NET 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hProcess`  
 (в) Ручка к процессу.  
  
 `pVersion`  
 (ваут) Буфер, содержащий строку числа версий после успешного завершения метода.  
  
 `cchBuffer`  
 (в) Длина буфера версии.  
  
 `pdwLength`  
 (ваут) Указатель на длину строки номера версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`pVersion`является недействительным `cchBuffer` и не является недействительным, или наоборот.<br /><br /> -или-<br /><br /> `hProcess`не является допустимой ручкой для процесса.<br /><br /> -или-<br /><br /> CLR не загружается.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`является нулевым или меньше, чем длина строки версии.|  
|E_NOTIMPL|Этот метод недоступен на операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
