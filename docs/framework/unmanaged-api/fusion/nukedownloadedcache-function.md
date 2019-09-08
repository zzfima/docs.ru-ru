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
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796308"
---
# <a name="nukedownloadedcache-function"></a>Функция NukeDownloadedCache
Удаляет кэш загрузки среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h.  
  
## <a name="remarks"></a>Примечания  
 Кэш загрузки среды CLR — это область, в которой хранятся сборки со строгими именами, загружаемые из URL-адреса для возможного повторного использования.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Библиотечная** Fusion. dll и mscorwks. dll. Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CreateHistoryReader](createhistoryreader-function.md)
- [Функция GetHistoryFileDirectory](gethistoryfiledirectory-function.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
