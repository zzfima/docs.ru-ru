---
title: 'Метод метод icordebugsymbolprovider:: Жетобжектсизе'
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: a5c0fe6d73302abbfabe2272cc878d6fd8f5fdec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138821"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a>Метод метод icordebugsymbolprovider:: Жетобжектсизе
Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbSignature`  
 [in] Число байтов в сигнатуре TypeSpec.  
  
 typeSig  
 [в] Сигнатура TypeSpec.  
  
 `pObjectSize`  
 [out] Указатель на размер объекта.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
