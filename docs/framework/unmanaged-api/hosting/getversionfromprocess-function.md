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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4015ecec38466650488a653641f5af93c4680f22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779594"
---
# <a name="getversionfromprocess-function"></a>Функция GetVersionFromProcess
Получает номер версии общей языковой среды выполнения (CLR), связанный с указанным дескриптором процесса.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
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
 [in] Дескриптор процесса.  
  
 `pVersion`  
 [out] Буфер, содержащий строку номера версии после успешного завершения метода.  
  
 `cchBuffer`  
 [in] Длина буфера версии.  
  
 `pdwLength`  
 [out] Указатель на длину строку номера версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`pVersion` имеет значение null и `cchBuffer` не равно null, или наоборот.<br /><br /> -или-<br /><br /> `hProcess` не является допустимым дескриптором к процессу.<br /><br /> -или-<br /><br /> Среда CLR не загружается.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer` равно null или меньше, чем длина строки версии.|  
|E_NOTIMPL|Этот метод не доступен в операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
