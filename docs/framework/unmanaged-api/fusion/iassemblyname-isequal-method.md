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
ms.openlocfilehash: f1fc128d15c56981f4bc6122e38e0514d006e29e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768619"
---
# <a name="iassemblynameisequal-method"></a>Метод IAssemblyName::IsEqual
Определяет, является ли заданное [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объект равен данному `IAssemblyName`, основываясь на флаги указанного сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pName`  
 [in] `IAssemblyName` Объекта, к которым должен сравниваться данный `IAssemblyName`.  
  
 `dwCmpFlags`  
 [in] Побитовое сочетание [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) значения, которые влияют на сравнение.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Версии NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
