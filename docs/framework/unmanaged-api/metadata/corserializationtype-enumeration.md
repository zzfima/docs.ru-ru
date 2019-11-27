---
title: Перечисление CorSerializationType
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
ms.openlocfilehash: 064374285216e9fb054b299937087f1ca7c351a4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432870"
---
# <a name="corserializationtype-enumeration"></a>Перечисление CorSerializationType
Указывает способ сериализации объекта средой CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|Сериализация объекта не определена.|  
|`SERIALIZATION_TYPE_BOOLEAN`|Объект сериализуется как логический тип|  
|`SERIALIZATION_TYPE_CHAR`|Объект сериализуется как символьный тип.|  
|`SERIALIZATION_TYPE_I1`|Объект сериализуется как целое число со знаком длиной 1 байт.|  
|`SERIALIZATION_TYPE_U1`|Объект сериализуется как 1-байтовое целое число без знака.|  
|`SERIALIZATION_TYPE_I2`|Объект сериализуется как 2-байтовое целое число со знаком.|  
|`SERIALIZATION_TYPE_U2`|Объект сериализуется как целое число без знака (2 байта).|  
|`SERIALIZATION_TYPE_I4`|Объект сериализуется как 4-байтовое целое число со знаком.|  
|`SERIALIZATION_TYPE_U4`|Объект сериализуется как 4-байтовое целое число без знака.|  
|`SERIALIZATION_TYPE_I8`|Объект сериализуется как 8-байтовое целое число со знаком.|  
|`SERIALIZATION_TYPE_U8`|Объект сериализуется как 8-байтное целое число без знака.|  
|`SERIALIZATION_TYPE_R4`|Объект сериализуется как 4-байтовое значение с плавающей запятой.|  
|`SERIALIZATION_TYPE_R8`|Объект сериализуется как 8-байтовое число с плавающей запятой.|  
|`SERIALIZATION_TYPE_STRING`|Объект сериализуется как тип System. String.|  
|`SERIALIZATION_TYPE_SZARRAY`|Объект сериализуется как одномерный массив с нулевой нижней границей.|  
|`SERIALIZATION_TYPE_TYPE`|Объект сериализуется как универсальный тип.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|Объект сериализуется как объект с тегами.|  
|`SERIALIZATION_TYPE_FIELD`|Объект сериализуется как поле.|  
|`SERIALIZATION_TYPE_PROPERTY`|Объект сериализуется как свойство.|  
|`SERIALIZATION_TYPE_ENUM`|Объект сериализуется как перечисление.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
