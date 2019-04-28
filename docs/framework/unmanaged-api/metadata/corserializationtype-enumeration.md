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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15b1f6be2dac6bc7566852791ac22e495949521c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992645"
---
# <a name="corserializationtype-enumeration"></a>Перечисление CorSerializationType
Задает способ сериализации объекта средой CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|Сериализация объекта не определено.|  
|`SERIALIZATION_TYPE_BOOLEAN`|Объект сериализуется как логический тип.|  
|`SERIALIZATION_TYPE_CHAR`|Объект сериализуется как тип символа.|  
|`SERIALIZATION_TYPE_I1`|Объект сериализуется как 1-байтовое целое число со знаком.|  
|`SERIALIZATION_TYPE_U1`|Объект сериализуется как 1-байтовое целое число без знака.|  
|`SERIALIZATION_TYPE_I2`|Объект сериализуется как целое число со знаком длиной 2 байта.|  
|`SERIALIZATION_TYPE_U2`|Объект сериализуется как целое число без знака длиной 2 байта.|  
|`SERIALIZATION_TYPE_I4`|Объект сериализуется как 4-байтовое целое число со знаком.|  
|`SERIALIZATION_TYPE_U4`|Объект сериализуется как 4-байтовое целое число без знака.|  
|`SERIALIZATION_TYPE_I8`|Объект сериализуется в виде целого числа со знаком размером 8 байт.|  
|`SERIALIZATION_TYPE_U8`|Объект сериализуется как целое число без знака размером 8 байт.|  
|`SERIALIZATION_TYPE_R4`|Объект сериализуется как 4-байтовое с плавающей запятой.|  
|`SERIALIZATION_TYPE_R8`|Объект сериализуется как с плавающей запятой размером 8 байт.|  
|`SERIALIZATION_TYPE_STRING`|Объект сериализуется как тип System.String.|  
|`SERIALIZATION_TYPE_SZARRAY`|Объект сериализуется как одномерный, нулевой нижней границы массива.|  
|`SERIALIZATION_TYPE_TYPE`|Объект сериализуется как универсальный тип.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|Объект сериализуется как объект с тегами.|  
|`SERIALIZATION_TYPE_FIELD`|Объект сериализуется как поле.|  
|`SERIALIZATION_TYPE_PROPERTY`|Объект сериализуется как свойство.|  
|`SERIALIZATION_TYPE_ENUM`|Объект сериализуется как перечисление.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
