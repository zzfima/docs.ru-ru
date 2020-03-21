---
title: Функция GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178115"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Функция GetRequestedRuntimeVersionForCLSID
Получает соответствующую информацию о времени выполнения общего языка (CLR) для класса с указанным `CLSID`.  
  
 Эта функция была унесена в системе .NET 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `rclsid`  
 (в)  Компонента. `CLSID`  
  
 `pVersion`  
 (ваут)  Буфер, содержащий строку номера версии после успешного завершения.  
  
 `cchBuffer`  
 (в)  Размер буфера, `pVersion` в широком характере.  
  
 `dwLength`  
 (ваут) Длина, в байтах, возвращенного буфера.  
  
 `dwResolutionFlags`  
 (в)  Одно из CLSID_RESOLUTION_FLAGS значений. Поддерживаются следующие значения.  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) указывает на то, что поведение интерп по умолчанию должно быть использовано.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) Указывает на то, что реестр должен быть проведен поиск и политика оболья должна быть применена.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Функция успешно возвращается.|  
|E_INVALIDARG|Один из параметров имеет недействительный тип или формат.|  
|ERROR_INSUFFICIENT_BUFFER|Буфер `pVersion` недостаточно велик, чтобы удерживать всю строку версии.|  
|REGDB_E_CLASSNOTREG|Нет класса, зарегистрированного `CLSID`с указанным .|  
|E_POINTER|`dwLength`является нулевым, или `cchBuffer` достаточно большим, чтобы `pVersion` держать строку версии, но является недействительным.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
