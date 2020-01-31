---
title: Метод ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 81993f108ae9b59300b5d29402d7a423c3657757
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792437"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>Метод ICorDebugProcess5::EnumerateGCReferences
Возвращает перечислитель для всех объектов, которые должны быть собраны в процессе сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `enumerateWeakReferences`  
 окне Логическое значение, указывающее, будут ли также перечисляться слабые ссылки. Если `enumerateWeakReferences` `true`, перечислитель `ppEnum` включает как строгие ссылки, так и слабые ссылки. Если `enumerateWeakReferences` `false`, перечислитель включает только строгие ссылки.  
  
 `ppEnum`  
 заполняет Указатель на адрес [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.  
  
## <a name="remarks"></a>Заметки  
 Этот метод предоставляет способ определения полной цепочки корневых объектов для любого управляемого объекта в процессе и может использоваться для определения причины, по которой объект остается в рабочем состоянии.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
