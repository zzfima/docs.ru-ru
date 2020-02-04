---
title: Метод ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: ba1cc8c91c53547c6ed4025ee67a69e253f3596d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783586"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>Метод ICorDebugDataTarget2::GetImageLocation
Возвращает путь для модуля из базового адреса модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `baseAddress`  
 окне Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.  
  
 `cchName`  
 [входной] Число символов в буфере, которые должен получить путь к модулю.  
  
 `pcchName`  
 [выходной] Указатель на число символов, записанных в буфер `szName`.  
  
 `szName`  
 [выходной] Путь к модулю.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
