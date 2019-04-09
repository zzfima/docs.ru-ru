---
title: Структура COR_IL_MAP
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6d8023c7ac6d917c9df40fb18316ddc12df5ec1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190435"
---
# <a name="corilmap-structure"></a>Структура COR_IL_MAP
Указывает изменения в относительном смещении функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`oldOffset`|Старый Microsoft промежуточного языка MSIL смещение относительно начала функции.|  
|`newOffset`|Новое смещение MSIL относительно начала функции.|  
|`fAccurate`|`true` Если сопоставление является точным; в противном случае `false`.|  
  
## <a name="remarks"></a>Примечания  
 Формат сопоставления выглядит следующим образом: Отладчик предполагается, что `oldOffset` ссылается на смещение MSIL в исходном, неизмененном MSIL-код. `newOffset` Параметр ссылается на соответствующее смещение MSIL в новом коде инструментированной.  
  
 Для начала работы должным образом, должны выполняться следующие требования:  
  
-   Карты должны быть отсортированы в порядке возрастания.  
  
-   Не требуется изменить порядок инструментированный код MSIL.  
  
-   Не следует удалять исходный код MSIL.  
  
-   Схема должна включать элементы для сопоставления всех точек следования из файла базы данных (PDB) программы.  
  
 Карты не интерполирует недостающие записи. Следующий пример показывает, карты и его результаты.  
  
 Карта:  
  
-   Старое смещение, 0, 0 новое смещение  
  
-   Старое смещение, 5, 10 новое смещение  
  
-   Старое смещение, 9, 20 новое смещение  
  
 Результаты:  
  
-   Старое смещение 0, 1, 2, 3 или 4 будет сопоставляться новое смещение 0.  
  
-   Старое смещение 5, 6, 7 или 8 будет сопоставляться новое смещение 10.  
  
-   Старое смещение 9 или более поздней версии будет сопоставляться новое смещение 20.  
  
-   Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлен старое смещение 0.  
  
-   Новое смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлен старое смещение 5.  
  
-   Новое смещение 20 или более поздней версии будет сопоставлен старое смещение 9.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
