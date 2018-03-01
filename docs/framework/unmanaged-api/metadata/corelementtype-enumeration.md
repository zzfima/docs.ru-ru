---
title: CorElementType Enumeration1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00f4aa4e87c0deb4b1326cb8bf4256a9307b3393
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corelementtype-enumeration1"></a>CorElementType Enumeration1
Указывает, среда выполнения <xref:System.Type>, модификатор типа или сведения о типе в сигнатуре типа метаданных.  
  
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
  
|Член|Описание:|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|Используется внутренним образом.|  
|`ELEMENT_TYPE_VOID`|Значение типа void.|  
|`ELEMENT_TYPE_BOOLEAN`|Логический тип.|  
|`ELEMENT_TYPE_CHAR`|Тип символа.|  
|`ELEMENT_TYPE_I1`|1-байтовое целое число со знаком.|  
|`ELEMENT_TYPE_U1`|1-байтовое целое число без знака.|  
|`ELEMENT_TYPE_I2`|2-байтовое целое число со знаком.|  
|`ELEMENT_TYPE_U2`|2-байтовое целое число без знака.|  
|`ELEMENT_TYPE_I4`|4-байтовое целое число со знаком.|  
|`ELEMENT_TYPE_U4`|4-байтовое целое число без знака.|  
|`ELEMENT_TYPE_I8`|8-байтовое целое число со знаком.|  
|`ELEMENT_TYPE_U8`|8-байтовое целое число без знака.|  
|`ELEMENT_TYPE_R4`|4-байтовое число с плавающей запятой.|  
|`ELEMENT_TYPE_R8`|8-байтовое число с плавающей запятой.|  
|`ELEMENT_TYPE_STRING`|Тип System.String.|  
|`ELEMENT_TYPE_PTR`|Модификатор типа указателя.|  
|`ELEMENT_TYPE_BYREF`|Модификатор ссылочного типа.|  
|`ELEMENT_TYPE_VALUETYPE`|Модификатор типа значения.|  
|`ELEMENT_TYPE_CLASS`|Модификатор типа класса.|  
|`ELEMENT_TYPE_VAR`|Модификатор типа переменной.|  
|`ELEMENT_TYPE_ARRAY`|Модификатор типа многомерного массива.|  
|`ELEMENT_TYPE_GENERICINST`|Модификатор типа для универсальных типов.|  
|`ELEMENT_TYPE_TYPEDBYREF`|Типизированная ссылка.|  
|`ELEMENT_TYPE_I`|Размер собственного целого числа со знаком.|  
|`ELEMENT_TYPE_U`|Размер собственного целое число без знака.|  
|`ELEMENT_TYPE_FNPTR`|Указатель на функцию.|  
|`ELEMENT_TYPE_OBJECT`|Тип System.Object.|  
|`ELEMENT_TYPE_SZARRAY`|Одномерный, модификатор типа нулевой нижней границы массива.|  
|`ELEMENT_TYPE_MVAR`|Модификатор типа переменной метода.|  
|`ELEMENT_TYPE_CMOD_REQD`|Обязательный модификатор языка c.|  
|`ELEMENT_TYPE_CMOD_OPT`|Необязательный модификатор языка C.|  
|`ELEMENT_TYPE_INTERNAL`|Используется внутренним образом.|  
|`ELEMENT_TYPE_MAX`|Недопустимый тип.|  
|`ELEMENT_TYPE_MODIFIER`|Используется внутренним образом.|  
|`ELEMENT_TYPE_SENTINEL`|Модификатор типа, который является sentinel список переменное количество параметров.|  
|`ELEMENT_TYPE_PINNED`|Используется внутренним образом.|  
  
## <a name="remarks"></a>Примечания  
 Модификаторы типов образуют основу для представления более сложных типов. Объект `CorElementType` значение модификатора типа применяется к значению, немедленно следующий за ним в сигнатуре типа. Значение, которое следует за `CorElementType` значение модификатора типа может быть `CorElementType` значение простого типа, маркер метаданных или другое значение, как указано в следующей таблице.  
  
> [!NOTE]
>  Все числа (*номер*, *счетчик аргументов*, *токен метаданных*, *ранг*, *число*и *привязан*) хранятся в виде сжатых целых чисел. В разделе [стандарту ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) на сайте ECMA подробные сведения.  
  
|Модификатор типа|Формат|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR < `CorElementType` значение >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF < `CorElementType` значение >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE < `mdTypeDef` токен метаданных >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS < `mdTypeDef` токен метаданных >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<число >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY < `CorElementType` значение > \<ранг > \<count1 > \<bound1 >... \<countN > \<boundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST < `mdTypeDef` токен метаданных > \<аргумент Count > \<аргумент1 >... \<argN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<Полная сигнатура для функции, включая соглашение о вызовах >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY < `CorElementType` значение >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<число >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ < `mdTypeRef` или `mdTypeDef` токен метаданных >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT < `mdTypeRef` или `mdTypeDef` токен метаданных >|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
