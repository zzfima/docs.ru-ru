---
title: Метод ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24671c371ae8a0a9f3c7ca650a71298c69e2fae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955676"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a>Метод ICorDebugSymbolProvider::GetMethodLocalSymbols
Получает локальные символы метода с учетом относительного виртуального адреса (RVA) этого метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nativeRVA`  
 [in] Собственный относительный виртуальный адрес метода.  
  
 `cRequestedSymbols`  
 [in] Количество запрошенных локальных символов.  
  
 `pcFetchedSymbols`  
 [out] Указатель на число  символов, полученных при помощи метода.  
  
 `pcFetchedSymbols`  
 заполняет Указатель на массив [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) , содержащий локальные символы метода.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetMethodParameterSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
