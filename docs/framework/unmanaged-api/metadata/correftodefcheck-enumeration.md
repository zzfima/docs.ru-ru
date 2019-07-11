---
title: Перечисление CorRefToDefCheck
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ae87dd4538a9a8e88591f498c0ce77b51bfa852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781620"
---
# <a name="correftodefcheck-enumeration"></a>Перечисление CorRefToDefCheck
Задает флаги для элемента управления, на который ссылаются элементы, преобразуемые в их определения для оптимизации кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDRefToDefDefault`|Указывает, что тип ссылки и ссылки на член должно быть преобразовано в определения. Это значение по умолчанию (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).|  
|`MDRefToDefAll`|Указывает, что все элементы, на которые имеются ссылки, должны преобразовываться к определениям.|  
|`MDRefToDefNone`|Указывает, что не ссылаются элементы должны быть преобразованы в определения.|  
|`MDTypeRefToDef`|Указывает, что только ссылки на тип должно быть преобразовано в тип определения.|  
|`MDMemberRefToDef`|Указывает, что только ссылки на член должно быть преобразовано в определения. То есть ссылки на элементы должны преобразовываться в определения метода или определения полей.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
