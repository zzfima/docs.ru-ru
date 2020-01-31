---
title: Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785640"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions
Перечисляет указанные области памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `callback`  
 окне Указатель на экземпляр [иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md) , вызываемый этим методом для каждой области памяти, перечисленной для уведомления отладчика о результатах.  
  
 Перечисление областей памяти продолжится, даже если обратный вызов указывает на сбой.  
  
 `miniDumpFlags`  
 окне Не используется.  
  
 `clrFlags`  
 окне Значение перечисления [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) , указывающее области памяти для перечисления.  
  
## <a name="remarks"></a>Заметки  
 Этот метод использует указанный экземпляр [иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md) для уведомления вызывающего объекта о результатах.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)
