---
title: Перечисление CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49784a0eba0458a7b9ddbcd58cbe1a187c3c779a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101215"
---
# <a name="corattributetargets-enumeration"></a>Перечисление CorAttributeTargets
Задает элементы приложения, в которых допустимо применять аргумент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`catAssembly`|Атрибут может быть применен к сборке.|  
|`catModule`|Атрибут может применяться для переносимого исполняемого модуля (.dll или .exe).|  
|`catClass`|Атрибут может быть применен к классу.|  
|`catStruct`|Атрибут может быть применен к структуре; то есть значение type.|  
|`catEnum`|Атрибут может быть применен к перечислению.|  
|`catConstructor`|Атрибут может применяться к конструктору.|  
|`catMethod`|Атрибут может применяться к методу.|  
|`catProperty`|Атрибут может быть применен к свойству.|  
|`catField`|Атрибут может быть применен к полю.|  
|`catEvent`|Атрибут может применяться к событию.|  
|`catInterface`|Атрибут может применяться к интерфейсу.|  
|`catParameter`|Атрибут может быть применен к параметру.|  
|`catDelegate`|Атрибут может быть применен к делегату.|  
|`catGenericParameter`|Атрибут может применяться к универсальному параметру.|  
|`catAll`|Атрибут может применяться к любому элементу приложения.|  
|`catClassMembers`|Атрибут может быть применен к члену класса.|  
  
## <a name="remarks"></a>Примечания  
 `CorAttributeTargets` Значения перечисления могут объединяться с помощью побитовой операции OR для получения необходимого сочетания.  
  
 `CorAttributeTargets` Параллельно управляемого <xref:System.AttributeTargets?displayProperty=nameWithType> перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
