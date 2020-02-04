---
title: Метод ICorDebugProcess5::GetTypeForTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: bb25c9235e4fcded5c230d2d417b9d41bbdd9b19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792339"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a>Метод ICorDebugProcess5::GetTypeForTypeID
Преобразует идентификатор типа в значение ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 окне Идентификатор типа.  
  
 `ppType`  
 заполняет Указатель на адрес объекта ICorDebugType.  
  
## <a name="remarks"></a>Заметки  
 В некоторых случаях методы, возвращающие идентификатор типа, могут возвращать значение NULL `COR_TYPEID`. Если это значение передается в качестве аргумента `id`, метод `GetTypeForTypeID` завершится ошибкой и возвратит `E_FAIL`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
