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
ms.openlocfilehash: ce0c6307defd93dcf63ac4e9051fc798041475f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127058"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Функция GetRequestedRuntimeVersionForCLSID
Возвращает соответствующую информацию о версии среды CLR для класса с указанным `CLSID`.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
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
 окне  `CLSID` компонента.  
  
 `pVersion`  
 заполняет  Буфер, содержащий строку номера версии после успешного завершения.  
  
 `cchBuffer`  
 окне  Размер `pVersion`ного буфера в расширенных символах.  
  
 `dwLength`  
 заполняет Длина возвращенного буфера в байтах.  
  
 `dwResolutionFlags`  
 окне  Одно из значений CLSID_RESOLUTION_FLAGS. Поддерживаются следующие значения:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) указывает, что следует использовать режим взаимодействия по умолчанию.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) указывает, что необходимо выполнять поиск в реестре и применять политику оболочки совместимости.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Функция возвращена успешно.|  
|E_INVALIDARG|Один из параметров имеет недопустимый тип или формат.|  
|ERROR_INSUFFICIENT_BUFFER|Буфер `pVersion` недостаточно велик для размещения всей строки версии.|  
|REGDB_E_CLASSNOTREG|Отсутствует класс, зарегистрированный в указанном `CLSID`.|  
|E_POINTER|`dwLength` имеет значение null, или `cchBuffer` достаточно большой для хранения строки версии, но `pVersion` имеет значение null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
