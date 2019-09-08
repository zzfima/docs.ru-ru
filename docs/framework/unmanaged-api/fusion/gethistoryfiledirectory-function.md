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
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796847"
---
# <a name="gethistoryfiledirectory-function"></a>Функция GetHistoryFileDirectory
Возвращает путь к каталогу журнала приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wzDir`  
 заполняет Буфер для хранения пути к каталогу журнала приложения.  
  
 `pdwSize`  
 [вход, выход] Длина буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает коды стандартных ошибок COM, как определено в файле WinError. h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`wzDir`или `pdwSize` имеет значение null, или строка версии неверна.|  
  
## <a name="remarks"></a>Примечания  
 При успешном завершении `pdwSize` аргументу присваивается длина строки пути.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Библиотечная** Fusion. dll и mscorwks. dll. Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CreateHistoryReader](createhistoryreader-function.md)
- [Функция NukeDownloadedCache](nukedownloadedcache-function.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
