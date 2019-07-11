---
title: Функция GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10eead2772a2bbd8abaf7b9c090a091687725972
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778654"
---
# <a name="gethistoryfiledirectory-function"></a>Функция GetHistoryFileDirectory
Извлекает путь к каталогу журнала приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wzDir`  
 [out] Буфер для хранения пути к каталогу журнала приложения.  
  
 `pdwSize`  
 [in, out] Длина буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`wzDir` или `pdwSize` имеет значение null, или версии Неверная строка.|  
  
## <a name="remarks"></a>Примечания  
 При успешном завершении `pdwSize` аргумент имеет значение длины строки пути.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Библиотека:** Fusion.dll и "Mscorwks.dll". Используйте Fusion.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [Функция NukeDownloadedCache](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
