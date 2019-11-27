---
title: Перечисление CorSymAddrKind
ms.date: 03/30/2017
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
ms.openlocfilehash: 12f31d0bf224e38418818122dad3586ec687b2ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448575"
---
# <a name="corsymaddrkind-enumeration"></a>Перечисление CorSymAddrKind
Указывает тип адреса памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Указывает локальную переменную или индекс параметра промежуточного языка MSIL.|  
|`ADDR_NATIVE_RVA`|Указывает относительный виртуальный адрес в модуле.|  
|`ADDR_NATIVE_REGISTER`|Указывает регистр ЦП.|  
|`ADDR_NATIVE_REGREL`|Указывает, что первый адрес является регистром, а второй — смещением.|  
|`ADDR_NATIVE_OFFSET`|Указывает смещение от базового адреса.|  
|`ADDR_NATIVE_REGREG`|Указывает, что первый адрес является нижней частью регистра, а второй адрес — верхней частью.|  
|`ADDR_NATIVE_REGSTK`|Указывает, что первый адрес является нижней частью регистра, второй — верхней частью, а третья — смещением.|  
|`ADDR_NATIVE_STKREG`|Указывает, что первый адрес является регистром, второй — смещением, а третье — старшая часть регистра.|  
|`ADDR_BITFIELD`|Указывает, что первым адресом является начало поля, а вторым адресом является длина поля.|  
|`ADDR_NATIVE_ISECTOFFSET`|Указывает, что первый адрес является разделом, а второй — смещением.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Перечисления хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
