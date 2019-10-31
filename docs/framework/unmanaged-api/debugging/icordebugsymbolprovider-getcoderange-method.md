---
title: 'Метод метод icordebugsymbolprovider:: GetCodeRange'
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 84bf545fedf3a6c7915d94fd0c2630268585b6eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138924"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>Метод метод icordebugsymbolprovider:: GetCodeRange
Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `codeRva`  
 [in] Относительный виртуальный адрес (RVA) в методе.  
  
 `pCodeStartAddress`  
 [out] Указатель на начальный адрес метода.  
  
 `pCodeSize`  
 Указатель на размер кода метода (число байтов кода метода).  
  
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
