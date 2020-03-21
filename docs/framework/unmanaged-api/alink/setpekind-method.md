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
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179392"
---
# <a name="setpekind-method"></a>Метод SetPEKind
Определяет портативный исполняемый тип, либо машинно-специфический, либо машинно-агностик.  
  
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
 Идентификатор сборки.  
  
 `FileToken`  
 Токен файла, для которого должен быть установлен тип PE. Может быть `AssemblyID` NULL, если не указывается несвязанный нетмодуль.  
  
 `dwPEKind`  
 Тип PE, как указано [в CorPEKind Enumeration](../metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Архитектура целевой машины, как указано в заголовке NT.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод успешно.  
  
## <a name="requirements"></a>Требования  
 Требуетa alink.h.  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
