---
title: Метод ICorDebugMergedAssemblyRecord::GetPublicKeyToken
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4a8e5f99a845d2befe55f5939b41224f2aa47b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077307"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>Метод ICorDebugMergedAssemblyRecord::GetPublicKeyToken
Возвращает токен открытого ключа сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbPublicKeyToken`  
 [in] Максимальное число байтов в массиве `pbPublicKeyToken`.  
  
 `pcbPublicKeyToken`  
 [out] Указатель на фактическое число байтов, записанных в массив `pbPublicKeyToken`.  
  
 `pbPublicKeyToken`  
 [out] Указатель на массив байтов, содержащий токен открытого ключа сборки.  
  
## <a name="remarks"></a>Примечания  
 Токен открытого ключа сборки — это последние восемь байтов хэша SHA1 ее открытого ключа.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
