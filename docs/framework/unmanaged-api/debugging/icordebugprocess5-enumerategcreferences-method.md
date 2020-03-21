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
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178624"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>Метод ICorDebugProcess5::EnumerateGCReferences
Получает регистратор для всех объектов, которые должны быть собраны мусором в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `enumerateWeakReferences`  
 (в) Значение Boolean, которое указывает, должны ли также перечисляться слабые ссылки. Если `enumerateWeakReferences` `true`это `ppEnum` так, то перечисление включает в себя как сильные ссылки, так и слабые ссылки. Если `enumerateWeakReferences` `false`это так, то перечисление включает только сильные ссылки.  
  
 `ppEnum`  
 (ваут) Указатель на адрес [ICorDebugGCReferenceEnum,](icordebuggcreferenceenum-interface.md) который является регистратором для объектов, которые будут собраны мусором.  
  
## <a name="remarks"></a>Remarks  
 Этот метод позволяет определить полную цепочку укоренения для любого управляемого объекта в процессе и может быть использован для определения того, почему объект все еще жив.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
