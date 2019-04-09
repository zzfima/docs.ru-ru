---
title: Структура COR_TYPEID
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51104516008ffee0694c72733cb5f82b5ba6d8cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109867"
---
# <a name="cortypeid-structure"></a>Структура COR_TYPEID
Содержит идентификатор типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`token1`|Первый токен.|  
|`token2`|Второй маркер.|  
  
## <a name="remarks"></a>Примечания  
 `COR_TYPEID` Структура возвращается несколько методов отладки, которые предоставляют сведения об объектах, чтобы участвовать в сборе мусора. Он может затем передается как аргумент, другие методы отладки, предоставляющие дополнительные сведения об этом элементе. Например, путем перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объекта, вы можете извлечь отдельные [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объекты, представляющие отдельные объекты в управляемой куче. Затем можно передать `COR_TYPEID` значение из `COR_HEAPOBJECT.type` поле [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод для извлечения ICorDebugType объект, предоставляющий сведения о типе об объекте.  
  
 Объект `COR_TYPEID` объект должен быть непрозрачным. Не следует получить доступ к его отдельных полей или управления этим состоянием. Его единственная используется как идентификатор, который предоставляется в качестве `out` параметр в вызов метода и который может в свою очередь, можно передать в другие методы для предоставления дополнительных сведений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
