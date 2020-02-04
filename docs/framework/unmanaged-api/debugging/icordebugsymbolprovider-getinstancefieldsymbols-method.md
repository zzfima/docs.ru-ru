---
title: Метод ICorDebugSymbolProvider::GetInstanceFieldSymbols
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9c55ce4d36681e173047cfb51515a74899c5a9fe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791633"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a>Метод ICorDebugSymbolProvider::GetInstanceFieldSymbols
Получает символы поля экземпляра, которые соответствуют сигнатуре TypeSpec.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbSignature`  
 [in] Число байтов в массиве `typeSig`.  
  
 `typeSig`  
 [in] Массив байтов, содержащий сигнатуру `typespec`.  
  
 `cRequestedSymbols`  
 [in] Количество запрошенных символов.  
  
 `pcFetchedSymbols`  
 [out] Указатель на число  символов, полученных при помощи метода.  
  
 `pSymbols`  
 заполняет Указатель на массив [икордебугстатикфиелдсимбол](icordebugstaticfieldsymbol-interface.md) , содержащий запрошенные символы поля экземпляра.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод GetStaticFieldSymbols](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
