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
ms.openlocfilehash: e6c3c9b842bd823e8975661964480fd801779b2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450132"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDRefToDefDefault`|Указывает, что ссылки на типы и ссылки на элементы должны быть преобразованы в определения. Это значение по умолчанию (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).|  
|`MDRefToDefAll`|Указывает, что все элементы, на которые указывают ссылки, должны быть преобразованы в определения.|  
|`MDRefToDefNone`|Указывает, что не нужно преобразовывать элементы, на которые имеются ссылки, в определения.|  
|`MDTypeRefToDef`|Указывает, что только ссылки на типы должны быть преобразованы в определения типов.|  
|`MDMemberRefToDef`|Указывает, что только ссылки на элементы должны быть преобразованы в определения. То есть ссылки на элементы должны быть преобразованы в определения методов или определения полей.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
