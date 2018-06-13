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
ms.openlocfilehash: 54d239c3091b29424b26fbab4cb4eb9152ff9ad9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442170"
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
|`catAssembly`|Атрибут может применяться к сборке.|  
|`catModule`|Атрибут может применяться для переносимого исполняемого модуля (.dll или .exe).|  
|`catClass`|Атрибут может применяться к классу.|  
|`catStruct`|Атрибут может быть применен к структуре; то есть введите значение.|  
|`catEnum`|Атрибут может применяться к перечислению.|  
|`catConstructor`|Атрибут может применяться для конструктора.|  
|`catMethod`|Атрибут может применяться к методу.|  
|`catProperty`|Атрибут может применяться к свойству.|  
|`catField`|Атрибут может применяться к полю.|  
|`catEvent`|Атрибут может применяться к событию.|  
|`catInterface`|Атрибут может применяться к интерфейсу.|  
|`catParameter`|Атрибут может применяться к параметру.|  
|`catDelegate`|Атрибут может применяться к делегату.|  
|`catGenericParameter`|Атрибут может применяться для универсального параметра.|  
|`catAll`|Атрибут может применяться к любому элементу приложения.|  
|`catClassMembers`|Атрибут может применяться к члену класса.|  
  
## <a name="remarks"></a>Примечания  
 `CorAttributeTargets` Значения перечисления могут быть объединены с помощью побитовой операции или для получения необходимого сочетания.  
  
 `CorAttributeTargets` Параллельно управляемый <xref:System.AttributeTargets?displayProperty=nameWithType> перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
