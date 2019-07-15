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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1218ee76a3b7a2f501f87adf1e0bc8133d5329b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781348"
---
# <a name="ceesectionreloctype-enumeration"></a>Перечисление CeeSectionRelocType
Предоставляет значения для влияния на тип `reloc` инструкции в вызове [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`srRelocAbsolute`|Создает только раздел относительно `reloc`отправляют ничего в раздел .reloc.|  
|`srRelocHighLow`|Создает `reloc` для расположения размера указателя. Это преобразуется в BASED_HIGHLOW или BASED_DIR64 зависимости от платформы.|  
|`srRelocHighAdj`|Создает `reloc` для старших 16 бит 32-разрядное число, в котором младшие 16 бит, включаются в следующего слова в таблице .reloc.|  
|`srRelocMapToken`|Создает перемещение сопоставления маркера, отправляя в раздел .reloc значение nothing.|  
|`srRelocRelative`|Указывает, что значение является относительной адресной привязкой.|  
|`srRelocFilePos`|Создает только раздел относительно `reloc`отправляют ничего в раздел .reloc. Это `reloc` относительно позиции файла данного раздела, а не виртуального адреса этого раздела.|  
|`srRelocCodeRelative`|Указывает адрес относительно кода адресной привязки.|  
|`srRelocIA64Imm64`|Создает `reloc` для 64-разрядные адреса в ia64 `movl` инструкции.|  
|`srRelocDir64`|Создает `reloc` для 64-разрядный адрес.|  
|`srRelocIA64PcRel25`|Создать `reloc` для 25-разрядного адреса относительно ПК в ia64 `br.call` инструкции.|  
|`srRelocIA64PcRel64`|Создает `reloc` для 64-разрядный адрес относительно ПК в ia64 `brl.call` инструкции.|  
|`srRelocAbsoluteTagged`|Создает раздел относительно 30-разрядного `reloc`, которое используется для значений указателей с тегами.|  
|`srRelocSentinel`|Значение-Метка для обеспечения любые дополнения для этого перечисления отражаются к внутреннему `reloc` в массиве имен.|  
|`srNoBaseReloc`|Указывает не выдавать базового `reloc`.|  
|`srRelocPtr`|Значение, указывающее, что содержимое предварительной адресной привязки памяти является указателем, а не раздела смещение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
