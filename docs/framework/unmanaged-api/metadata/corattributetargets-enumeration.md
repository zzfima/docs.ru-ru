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
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176205"
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
  
|Участник|Описание|  
|------------|-----------------|  
|`catAssembly`|Атрибут может быть применен к сборке.|  
|`catModule`|Атрибут может быть применен к переносному исполняемому (.dll или .exe) модулю.|  
|`catClass`|Атрибут может быть применен к классу.|  
|`catStruct`|Атрибут может быть применен к структуре, т.е. может являться типом значения.|  
|`catEnum`|Атрибут может быть применен к перечислению.|  
|`catConstructor`|Атрибут может быть применен к конструктору.|  
|`catMethod`|Атрибут может быть применен к методу.|  
|`catProperty`|Атрибут может быть применен к свойству.|  
|`catField`|Атрибут может быть применен к полю.|  
|`catEvent`|Атрибут может быть применен к событию.|  
|`catInterface`|Атрибут может быть применен к интерфейсу.|  
|`catParameter`|Атрибут может быть применен к параметру.|  
|`catDelegate`|Атрибут может быть применен к делегату.|  
|`catGenericParameter`|Атрибут может быть применен к универсальному параметру.|  
|`catAll`|Атрибут может быть применен к любому элементу приложения.|  
|`catClassMembers`|Атрибут может быть применен к члену класса.|  
  
## <a name="remarks"></a>Remarks  
 Значения `CorAttributeTargets` перечисления могут быть объединены с bitwise или операции, чтобы получить предпочтительную комбинацию.  
  
 Параллели `CorAttributeTargets` управляемого <xref:System.AttributeTargets?displayProperty=nameWithType> перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
