---
title: Перечисление1 CorElementType
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5112c3c8d5fef6efada4bffdfa575716503515e6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488252"
---
# <a name="corelementtype-enumeration1"></a>Перечисление1 CorElementType
Указывает, среда CLR <xref:System.Type>, модификатор типа или сведения о типе в сигнатуре типа метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|Используется внутренним образом.|  
|`ELEMENT_TYPE_VOID`|Значение типа void.|  
|`ELEMENT_TYPE_BOOLEAN`|Логический тип.|  
|`ELEMENT_TYPE_CHAR`|Тип символа.|  
|`ELEMENT_TYPE_I1`|1-байтовое целое число со знаком.|  
|`ELEMENT_TYPE_U1`|1-байтовое целое число без знака.|  
|`ELEMENT_TYPE_I2`|Целое число со знаком длиной 2 байта.|  
|`ELEMENT_TYPE_U2`|2-байтовое целое число без знака.|  
|`ELEMENT_TYPE_I4`|4-байтовое целое число со знаком.|  
|`ELEMENT_TYPE_U4`|4-байтовое целое число без знака.|  
|`ELEMENT_TYPE_I8`|8-байтное целое число со знаком.|  
|`ELEMENT_TYPE_U8`|8-байтовое целое число без знака.|  
|`ELEMENT_TYPE_R4`|4-байтовое с плавающей запятой.|  
|`ELEMENT_TYPE_R8`|8-байтовое с плавающей запятой.|  
|`ELEMENT_TYPE_STRING`|Тип System.String.|  
|`ELEMENT_TYPE_PTR`|Модификатор типа указателя.|  
|`ELEMENT_TYPE_BYREF`|Модификатор ссылочного типа.|  
|`ELEMENT_TYPE_VALUETYPE`|Модификатор типа значения.|  
|`ELEMENT_TYPE_CLASS`|Модификатор типа класса.|  
|`ELEMENT_TYPE_VAR`|Модификатор типа переменной.|  
|`ELEMENT_TYPE_ARRAY`|Модификатор типа многомерного массива.|  
|`ELEMENT_TYPE_GENERICINST`|Модификатор типа для универсальных типов.|  
|`ELEMENT_TYPE_TYPEDBYREF`|Типизированная ссылка.|  
|`ELEMENT_TYPE_I`|Размер собственного целого числа.|  
|`ELEMENT_TYPE_U`|Размер собственного целое число без знака.|  
|`ELEMENT_TYPE_FNPTR`|Указатель на функцию.|  
|`ELEMENT_TYPE_OBJECT`|Тип System.Object.|  
|`ELEMENT_TYPE_SZARRAY`|Создает одномерный, модификатор типа нулевой нижней границы массива.|  
|`ELEMENT_TYPE_MVAR`|Модификатор типа переменной метода.|  
|`ELEMENT_TYPE_CMOD_REQD`|Обязательный модификатор языка C|  
|`ELEMENT_TYPE_CMOD_OPT`|Необязательный модификатор языка C.|  
|`ELEMENT_TYPE_INTERNAL`|Используется внутренним образом.|  
|`ELEMENT_TYPE_MAX`|Недопустимый тип.|  
|`ELEMENT_TYPE_MODIFIER`|Используется внутренним образом.|  
|`ELEMENT_TYPE_SENTINEL`|Модификатор типа, который является sentinel список переменное количество параметров.|  
|`ELEMENT_TYPE_PINNED`|Используется внутренним образом.|  
  
## <a name="remarks"></a>Примечания  
 Модификаторы типа формируют основу для представления более сложных типов. Объект `CorElementType` значение модификатора типа применяется к значению, следующим непосредственно за ним в сигнатуре типа. Значение, которое следует за `CorElementType` значение модификатора типа может быть `CorElementType` значение простого типа, маркер метаданных или другое значение, как указано в следующей таблице.  
  
> [!NOTE]
>  Все числа (*номер*, *счетчик аргументов*, *токен метаданных*, *ранг*, *число*и *привязан*) хранятся в виде сжатых целых чисел. См. в разделе [стандарт ECMA-335 — Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) ECMA на веб-сайте сведения.  
  
|Модификатор типа|Формат|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR < `CorElementType` значение >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF < `CorElementType` значение >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE < `mdTypeDef` токен метаданных >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS < `mdTypeDef` токен метаданных >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<номер >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY < `CorElementType` значение > \<ранг > \<count1 > \<bound1 >... \<countN > \<boundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST < `mdTypeDef` токен метаданных > \<аргумент Count > \<arg1 >... \<argN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<Полная сигнатура для функции, включая соглашение о вызовах >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY < `CorElementType` значение >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<номер >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ < `mdTypeRef` или `mdTypeDef` маркер метаданных >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT < `mdTypeRef` или `mdTypeDef` маркер метаданных >|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
