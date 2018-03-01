---
title: "Перечисление CorSymAddrKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 300913f9ea89044e425f9f05856d13fa15cdc015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corsymaddrkind-enumeration"></a>Перечисление CorSymAddrKind
Указывает тип адреса памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Указывает Microsoft промежуточного языка MSIL индекс локальной переменной или параметра.|  
|`ADDR_NATIVE_RVA`|Указывает относительный виртуальный адрес в модуль.|  
|`ADDR_NATIVE_REGISTER`|Указывает регистр ЦП.|  
|`ADDR_NATIVE_REGREL`|Указывает, что первый адрес является регистром, а второй адрес — это смещение.|  
|`ADDR_NATIVE_OFFSET`|Указывает смещение от базового адреса.|  
|`ADDR_NATIVE_REGREG`|Указывает, что первый адрес является нижней частью регистра, а второй — верхней.|  
|`ADDR_NATIVE_REGSTK`|Указывает, что первый адрес является нижней частью регистра и второй — верхней, а третий — это смещение.|  
|`ADDR_NATIVE_STKREG`|Указывает, что первый адрес является регистром, второй — смещением и третий — верхней регистра.|  
|`ADDR_BITFIELD`|Указывает, что первый адрес является началом поля, а второй — длина поля.|  
|`ADDR_NATIVE_ISECTOFFSET`|Указывает, что первый адрес является разделом и второй адрес — это смещение.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Перечисления хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
