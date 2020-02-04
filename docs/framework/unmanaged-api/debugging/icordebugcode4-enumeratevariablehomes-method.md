---
title: 'Метод ICorDebugCode4:: Енумератевариаблехомес'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: ca452b230e2508f2d69c9aa38f274db506f3a906
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784091"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>Метод ICorDebugCode4:: Енумератевариаблехомес
Возвращает перечислитель для локальных переменных и аргументов в функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 Указатель на адрес объекта интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) , который является перечислителем для локальных переменных и аргументов в функции.  
  
## <a name="remarks"></a>Заметки  
 Объект интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) является стандартным перечислителем, производным от интерфейса "ICorDebugEnum", который позволяет перечислить объекты [ICorDebugVariableHome](icordebugvariablehome-interface.md) . Коллекция может содержать несколько объектов [ICorDebugVariableHome](icordebugvariablehome-interface.md) для одного и того же индекса слота или аргумента, если они имеют разные расположения в разных точках функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugCode4](icordebugcode4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
