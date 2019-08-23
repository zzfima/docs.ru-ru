---
title: Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f7859b095d80edb5592af1386457ad72b85bc48
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957385"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a>Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords
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
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
