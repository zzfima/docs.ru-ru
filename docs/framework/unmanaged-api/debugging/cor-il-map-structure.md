---
title: "Структура COR_IL_MAP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e2772833d75ced2209896ca37cf6cf37fb965f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
  
|Член|Описание:|  
|------------|-----------------|  
|`oldOffset`|Старый промежуточный язык Майкрософт (MSIL) смещение относительно начала функции.|  
|`newOffset`|Новое смещение MSIL относительно начала функции.|  
|`fAccurate`|`true`Если сопоставление является точным; в противном случае `false`.|  
  
## <a name="remarks"></a>Примечания  
 Карты имеет следующий формат: отладчик предполагается, что `oldOffset` ссылается на смещение MSIL в пределах исходного, неизмененного MSIL-код. `newOffset` Параметр ссылается на соответствующее смещение MSIL в новом инструментированном коде.  
  
 Для начала работы должным образом, должны выполняться следующие требования:  
  
-   Карты должны быть отсортированы в порядке возрастания.  
  
-   Не требуется изменить порядок инструментированный код MSIL.  
  
-   Не следует удалять исходный код MSIL.  
  
-   При сопоставлении должны учитываться записи для сопоставления всех точек следования из файла базы данных (PDB) программы.  
  
 Карты не выполнять интерполяцию, отсутствующие записи. В следующем примере показано сопоставление и его результаты.  
  
 Карта:  
  
-   0 старое смещение, 0 новое смещение  
  
-   5 старое смещение, 10 новое смещение  
  
-   9 старое смещение, 20 новое смещение  
  
 Результаты:  
  
-   Старое смещение 0, 1, 2, 3 или 4 будет сопоставлено новому смещению 0.  
  
-   Старое смещение 5, 6, 7 или 8 будет сопоставлено новому смещению 10.  
  
-   Старое смещение 9 или более поздней версии будут сопоставлены новому смещению 20.  
  
-   Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлено старому смещению 0.  
  
-   Новый смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлено старому смещению 5.  
  
-   Новое смещение 20 или выше будет сопоставлено старому смещению 9.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
