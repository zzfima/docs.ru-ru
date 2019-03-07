---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageBytes
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c44260d3b5baa18bc24f85cdbea94016b43291e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489791"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a>Метод ICorDebugSymbolProvider::GetAssemblyImageBytes
Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `rva`  
 [in] Относительный виртуальный адрес (RVA) в объединенной сборке.  
  
 `length`  
 Число байт для чтения из объединенной сборки.  
  
 `ppMemoryBuffer`  
 Указатель на адрес [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) , содержащий сведения о буфере памяти с метаданными объединенной сборки.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
