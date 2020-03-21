---
title: Метод ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 94882c67752705f9f13b858ae3b386a19dc103a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178559"
---
# <a name="icordebugprocess6getcode-method"></a>Метод ICorDebugProcess6::GetCode
Получает информацию об управляемом коде по адресу определенного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a>Параметры  
 `codeAddress`  
 (в) Значение [CORDB_ADDRESS,](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) окоторомявающие начальный адрес управляемого сегмента кода.  
  
 `ppCode`  
 (ваут) Указатель на адрес объекта "ICorDebugCode", представляющий сегмент управляемого кода.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
