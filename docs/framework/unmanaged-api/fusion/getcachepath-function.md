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
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132699"
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
 [вход, выход] Запрошенная максимальная длина `pwzCachePath`и, при возврате, фактической длины `pwzCachePath`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
