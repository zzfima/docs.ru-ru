---
title: Функция NukeDownloadedCache
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0436991512713c05e60a3c10d6fbdaa17bb378c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nukedownloadedcache-function"></a>Функция NukeDownloadedCache
Удаляет кэше загрузки среды выполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h.  
  
## <a name="remarks"></a>Примечания  
 Кэш загрузки среды CLR — это область, где хранятся сборки со строгими именами, загруженных из URL-адреса для возможного повторного использования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Библиотека:** Fusion.dll и Mscorwks.dll. Используйте Fusion.dll вместо Mscorwks.dll, чтобы целевая правильную версию платформы .NET Framework.  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [Функция GetHistoryFileDirectory](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
