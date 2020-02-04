---
title: Метод ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782292"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a>Метод ICorDebugInstanceFieldSymbol::GetOffset
Возвращает смещение в байтах этого поля экземпляра в его родительском классе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pcbOffset`  
 Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
