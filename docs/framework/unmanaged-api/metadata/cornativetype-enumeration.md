---
title: Перечисление CorNativeType
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf62000fd4ec5c8f3dea3fa7d560b3f9ead33fa7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045473"
---
# <a name="cornativetype-enumeration"></a>Перечисление CorNativeType
Содержит значения, описывающие собственные неуправляемые типы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|Является устаревшей.|  
|`NATIVE_TYPE_VOID`|Является устаревшей.|  
|`NATIVE_TYPE_BOOLEAN`|4-байтовое логическое значение, где значение TRUE, ненулевое значение и значение FALSE, равно нулю.|  
|`NATIVE_TYPE_I1`|8-разрядное целое число со знаком.|  
|`NATIVE_TYPE_U1`|8-разрядное целочисленное значение без знака.|  
|`NATIVE_TYPE_I2`|16-разрядное целое число со знаком.|  
|`NATIVE_TYPE_U2`|16-разрядное целочисленное значение без знака.|  
|`NATIVE_TYPE_I4`|32-разрядное целое значение со знаком.|  
|`NATIVE_TYPE_U4`|32-разрядное целое значение без знака.|  
|`NATIVE_TYPE_I8`|Значение 64-битового знакового целого числа.|  
|`NATIVE_TYPE_U8`|64-разрядное целочисленное значение без знака.|  
|`NATIVE_TYPE_R4`|4-байтовое числовое значение с плавающей запятой.|  
|`NATIVE_TYPE_R8`|8-байтное числовое значение с плавающей запятой.|  
|`NATIVE_TYPE_SYSCHAR`|Является устаревшей.|  
|`NATIVE_TYPE_VARIANT`|Является устаревшей.|  
|`NATIVE_TYPE_CURRENCY`|Числовой тип COM, который соответствует управляемого <xref:System.Decimal> типа.|  
|`NATIVE_TYPE_PTR`|Является устаревшей.|  
|`NATIVE_TYPE_DECIMAL`|Является устаревшей.|  
|`NATIVE_TYPE_DATE`|Является устаревшей.|  
|`NATIVE_TYPE_BSTR`|COM-взаимодействия.|  
|`NATIVE_TYPE_LPSTR`|Строковое значение LPSTR.|  
|`NATIVE_TYPE_LPWSTR`|Строковое значение LPWSTR.|  
|`NATIVE_TYPE_LPTSTR`|Строковое значение LPTSTR.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|Фиксированное, системный строковое значение.|  
|`NATIVE_TYPE_OBJECTREF`|Является устаревшей.|  
|`NATIVE_TYPE_IUNKNOWN`|COM-взаимодействия.|  
|`NATIVE_TYPE_IDISPATCH`|COM-взаимодействия.|  
|`NATIVE_TYPE_STRUCT`|Значение собственной структуры.|  
|`NATIVE_TYPE_INTF`|COM-взаимодействия.|  
|`NATIVE_TYPE_SAFEARRAY`|COM-взаимодействия.|  
|`NATIVE_TYPE_FIXEDARRAY`|Значение массива фиксированной длины.|  
|`NATIVE_TYPE_INT`|Собственный 16-разрядное целое число со знаком.|  
|`NATIVE_TYPE_UINT`|Значение собственного 16-разрядное целое число без знака.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|Является устаревшей.<br /><br /> Используйте NATIVE_TYPE_STRUCT.|  
|`NATIVE_TYPE_BYVALSTR`|COM-взаимодействия.|  
|`NATIVE_TYPE_ANSIBSTR`|COM-взаимодействия.|  
|`NATIVE_TYPE_TBSTR`|COM-взаимодействия.<br /><br /> Выберите BSTR или ANSIBSTR в зависимости от платформы.|  
|`NATIVE_TYPE_VARIANTBOOL`|2-байтовое логическое значение, где значение TRUE — -1, а FALSE равно нулю.|  
|`NATIVE_TYPE_FUNC`|Указатель функции.|  
|`NATIVE_TYPE_ASANY`|Ссылка на машинный тип.|  
|`NATIVE_TYPE_ARRAY`|Ссылка на массив с членами незаданного типа.|  
|`NATIVE_TYPE_LPSTRUCT`|Указатель на структуру 32-разрядное целое число.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|Собственный тип настраиваемого модуля маршалинга.<br /><br /> Это следует указать строку в следующем формате: «Имя/0Custom упаковщик собственный тип типа имя/0Optional cookie/0» или «{собственного введите GUID} / упаковщик 0Custom введите имя/0Optional файл cookie или 0 "|  
|`NATIVE_TYPE_ERROR`|COM-взаимодействия.<br /><br /> С помощью ELEMENT_TYPE_I4 этот тип сопоставляется VT_HRESULT.|  
|`NATIVE_TYPE_IINSPECTABLE`|Собственный `IInspectable` типа.|  
|`NATIVE_TYPE_HSTRING`|Собственный `HString`.|  
|`NATIVE_TYPE_MAX`|Недопустимое значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
