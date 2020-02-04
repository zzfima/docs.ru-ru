---
title: Метод ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 306d881c05c2fcdb15a53a439bfce6eff3afffa8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792313"
---
# <a name="icordebugprocess5gettypelayout-method"></a>Метод ICorDebugProcess5::GetTypeLayout
Возвращает сведения о макете объекта в памяти на основе его идентификатора типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 окне Токен [COR_TYPEID](cor-typeid-structure.md) , указывающий тип, макет которого требуется.  
  
 `pLayout`  
 заполняет Указатель на структуру [COR_TYPE_LAYOUT](cor-type-layout-structure.md) , содержащую сведения о макете объекта в памяти.  
  
## <a name="remarks"></a>Заметки  
 Метод `ICorDebugProcess5::GetTypeLayout` предоставляет сведения об объекте на основе его [COR_TYPEID](cor-typeid-structure.md), который возвращается несколькими другими методами [метод ICorDebugProcess5](icordebugprocess5-interface.md) . Сведения предоставляются структурой [COR_TYPE_LAYOUT](cor-type-layout-structure.md) , которая заполняется методом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структура COR_TYPE_LAYOUT](cor-type-layout-structure.md)
- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
