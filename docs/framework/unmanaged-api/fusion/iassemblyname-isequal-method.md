---
title: Метод IAssemblyName::IsEqual
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 926bdcee3a3c3974c8546f3a6dfe98f0b62c93c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796569"
---
# <a name="iassemblynameisequal-method"></a>Метод IAssemblyName::IsEqual
Определяет, равен ли указанный объект [IAssemblyName](iassemblyname-interface.md) этому `IAssemblyName`объекту на основе указанных флагов сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pName`  
 окне Объект, с которым необходимо выполнить `IAssemblyName`сравнение. `IAssemblyName`  
  
 `dwCmpFlags`  
 окне Побитовое сочетание значений [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) , влияющих на сравнение.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Перечисления Fusion](fusion-enumerations.md)
