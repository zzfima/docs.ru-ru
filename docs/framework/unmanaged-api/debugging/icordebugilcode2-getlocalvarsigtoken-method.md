---
title: Метод ICorDebugILCode2::GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3759cfa330ac37d2ed62a0b8bb70b5e10cd9d12e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782450"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a>Метод ICorDebugILCode2::GetLocalVarSigToken
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pmdSig`  
 [из] Указатель на маркер `mdSignature` для подписи локальной переменной, предназначенной для этой функции, или `mdSignatureNil`, если подпись отсутствует (т. е. если функция не имеет локальных переменных).  
  
## <a name="remarks"></a>Заметки  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
