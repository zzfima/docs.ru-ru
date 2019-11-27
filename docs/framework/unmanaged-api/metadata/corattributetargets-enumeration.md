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
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443873"
---
# <a name="corattributetargets-enumeration"></a>Перечисление CorAttributeTargets
Задает элементы приложения, в которых допустимо применять аргумент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`catAssembly`|Атрибут может быть применен к сборке.|  
|`catModule`|Атрибут может применяться к переносимому исполняемому модулю (DLL или exe).|  
|`catClass`|Атрибут может применяться к классу.|  
|`catStruct`|Атрибут может быть применен к структуре; то есть тип значения.|  
|`catEnum`|Атрибут может применяться к перечислению.|  
|`catConstructor`|Атрибут может применяться к конструктору.|  
|`catMethod`|Атрибут может применяться к методу.|  
|`catProperty`|Атрибут может применяться к свойству.|  
|`catField`|Атрибут может применяться к полю.|  
|`catEvent`|Атрибут может применяться к событию.|  
|`catInterface`|Атрибут может применяться к интерфейсу.|  
|`catParameter`|Атрибут может применяться к параметру.|  
|`catDelegate`|Атрибут может применяться к делегату.|  
|`catGenericParameter`|Атрибут может применяться к универсальному параметру.|  
|`catAll`|Атрибут может применяться к любому элементу Application.|  
|`catClassMembers`|Атрибут может применяться к члену класса.|  
  
## <a name="remarks"></a>Примечания  
 Значения перечисления `CorAttributeTargets` можно сочетать с битовой операцией OR для получения предпочтительного сочетания.  
  
 `CorAttributeTargets` параллельно перечисление управляемых <xref:System.AttributeTargets?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
