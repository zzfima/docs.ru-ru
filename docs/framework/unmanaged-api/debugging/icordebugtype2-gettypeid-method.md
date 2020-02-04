---
title: 'Метод ICorDebugType2:: TypeID'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791230"
---
# <a name="icordebugtype2gettypeid-method"></a>Метод ICorDebugType2:: TypeID
Возвращает [COR_TYPEID](cor-typeid-structure.md) для этого типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 заполняет Указатель на [COR_TYPEID](cor-typeid-structure.md) для этого элемента ICorDebugType.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Ниже приведены коды `HRESULT`.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Метод получил допустимый [COR_TYPEID](cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|Тип не был загружен.|  
|`CORDBG_E_UNSUPPORTED`|Этот тип не поддерживается.|  
  
## <a name="remarks"></a>Заметки  
 Этот метод предоставляет сопоставление из объекта ICorDebugType, представляющего тип, который может быть или не загружен в среду выполнения, в [COR_TYPEID](cor-typeid-structure.md), который служит в качестве непрозрачного маркера, определяющего тип, загруженный в среду выполнения.  
  
 Если тип, который представляет объект ICorDebugType, еще не загружен, этот метод возвращает `CORDBG_E_CLASS_NOT_LOADED`.  Если тип не поддерживается, он возвращает `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugType2](icordebugtype2-interface.md)
