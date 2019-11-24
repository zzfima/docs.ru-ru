---
title: Метод EmitInternalExportedTypes
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
ms.openlocfilehash: d4b7064b0339825c29e4001bc35c4a604098468a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446495"
---
# <a name="emitinternalexportedtypes-method"></a>Метод EmitInternalExportedTypes
Emits types added to the assembly. Call this method after known internal types have been added.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 ID of assembly.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>Требования  
 Requires alink.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
