---
title: Функция GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796907"
---
# <a name="getcachepath-function"></a>Функция GetCachePath
Возвращает путь к кэшированной сборке с использованием указанных флагов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `dwCacheFlags`  
 окне Значение [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) , указывающее источник кэшированной сборки.  
  
 `pwzCachePath`  
 заполняет Возвращаемый указатель на путь.  
  
 `pcchPath`  
 [вход, выход] Запрошенная максимальная длина `pwzCachePath`и при возврате фактической `pwzCachePath`длины.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
