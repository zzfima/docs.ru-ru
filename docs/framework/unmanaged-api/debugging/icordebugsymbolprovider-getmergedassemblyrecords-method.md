---
title: 'Метод метод icordebugsymbolprovider:: Жетмержедассемблирекордс'
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 6faf8960c06488c8fff5a076aae375529e1d0260
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138885"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a>Метод метод icordebugsymbolprovider:: Жетмержедассемблирекордс
Возвращает символьные записи для всех объединенных сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cRequestedRecords`  
 [in] Количество запрошенных символьных записей.  
  
 `pcFetchedRecords`  
 [out] Указатель на число  символьных записей, полученных при помощи метода.  
  
 `pRecords`  
 Указатель на массив объектов [икордебугмержедассемблирекорд](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) .  
  
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
