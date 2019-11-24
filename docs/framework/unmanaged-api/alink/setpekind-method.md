---
title: Метод SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: dfbc10bdbe633450dee2e27524c29ead21fb739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445534"
---
# <a name="setpekind-method"></a>Метод SetPEKind
Determines the portable executable type, either machine-specific or machine-agnostic.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 ID of the assembly.  
  
 `FileToken`  
 Token of file for which the PE type is to be set. Can be NULL if `AssemblyID` does not indicate an unbound netmodule.  
  
 `dwPEKind`  
 The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 The target machine architecture, as indicated in the NT header.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>Требования  
 Requires alink.h.  
  
## <a name="see-also"></a>См. также

- [Метод GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
