---
title: Перечисление CeeSectionRelocType
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176218"
---
# <a name="ceesectionreloctype-enumeration"></a>Перечисление CeeSectionRelocType
Предоставляет значения для влияния `reloc` на тип инструкции, излучаемые в вызове к [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`srRelocAbsolute`|Генерирует только раздел-родственник, `reloc`ничего не отправляя в раздел .reloc.|  
|`srRelocHighLow`|Генерирует `reloc` место для указателя. Это превращается в BASED_HIGHLOW или BASED_DIR64 в зависимости от платформы.|  
|`srRelocHighAdj`|Генерирует `reloc` для топ 16 битов 32-битного числа, где нижние 16 битов включены в следующее слово в таблице .reloc.|  
|`srRelocMapToken`|Генерирует перемещение токенов карты, ничего не отправляя в раздел .reloc.|  
|`srRelocRelative`|Указывает, что значение является исправлением относительного адреса.|  
|`srRelocFilePos`|Генерирует только раздел-родственник, `reloc`ничего не отправляя в раздел .reloc. Это `reloc` относительно положения файла раздела, а не виртуального адреса раздела.|  
|`srRelocCodeRelative`|Установить исправление код-относительного адреса.|  
|`srRelocIA64Imm64`|Генерирует `reloc` 64-битный адрес в инструкции `movl` ia64.|  
|`srRelocDir64`|Генерирует `reloc` 64-разрядный адрес.|  
|`srRelocIA64PcRel25`|Создайте `reloc` для 25-битного PC-относительного адреса `br.call` в инструкции ia64.|  
|`srRelocIA64PcRel64`|Генерирует `reloc` 64-разрядный pc-относительный адрес в инструкции ia64. `brl.call`|  
|`srRelocAbsoluteTagged`|Генерирует 30-битный сечение-относительный, `reloc`используемый для помеченных значений указателя.|  
|`srRelocSentinel`|Значение дозорного, которое поможет обеспечить, чтобы любые `reloc` дополнения к этому эквайму были отражены во внутреннем массиве имен.|  
|`srNoBaseReloc`|Указывает не излучать базу. `reloc`|  
|`srRelocPtr`|Значение, указывающее на то, что предварительное исправление содержимого памяти является указателем, а не смещением секции.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
