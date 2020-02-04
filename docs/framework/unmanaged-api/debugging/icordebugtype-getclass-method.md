---
title: Метод ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791298"
---
# <a name="icordebugtypegetclass-method"></a>Метод ICorDebugType::GetClass
Возвращает указатель интерфейса на объект ICorDebugClass, представляющий универсальный тип, экземпляр которого не был создан.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppClass`  
 заполняет Указатель на адрес интерфейса `ICorDebugClass`, представляющий универсальный тип, экземпляр которого не был создан.  
  
## <a name="remarks"></a>Заметки  
 `GetClass` могут вызываться только при определенных условиях. Вызовите метод [ICorDebugType:: GetType](icordebugtype-gettype-method.md) перед вызовом `GetClass`. Если `ICorDebugType::GetType` возвращает значение Корелементтипе, которое является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, можно вызвать `GetClass`, чтобы получить неэкземплярный тип для универсального типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
