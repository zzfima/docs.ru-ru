---
title: 'Метод Икордебугмержедассемблирекорд:: Жетпубликкэйтокен'
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: 95ed1303b33b328d1f14ecea6cc318e14991cd54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129776"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>Метод Икордебугмержедассемблирекорд:: Жетпубликкэйтокен
Возвращает токен открытого ключа сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="remarks"></a>Заметки  
 Токен открытого ключа сборки — это последние восемь байтов хэша SHA1 ее открытого ключа.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
