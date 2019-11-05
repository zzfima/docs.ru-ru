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
ms.openlocfilehash: 8f97614412eb2d49b202e86bdabc727159deb5d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131689"
---
# <a name="nukedownloadedcache-function"></a>Функция NukeDownloadedCache
Удаляет кэш загрузки среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h.  
  
## <a name="remarks"></a>Заметки  
 Кэш загрузки среды CLR — это область, в которой хранятся сборки со строгими именами, загружаемые из URL-адреса для возможного повторного использования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Fusion. dll и mscorwks. dll. Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CreateHistoryReader](createhistoryreader-function.md)
- [Функция GetHistoryFileDirectory](gethistoryfiledirectory-function.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
