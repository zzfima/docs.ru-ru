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
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444155"
---
# <a name="ceesectionreloctype-enumeration"></a>Перечисление CeeSectionRelocType
Предоставляет значения, влияющие на тип инструкции `reloc`, выдаваемой при вызове метода [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
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
  
|Член|Описание|  
|------------|-----------------|  
|`srRelocAbsolute`|Создает только относительный `reloc`раздела, отправляя в раздел. reloc значение Nothing.|  
|`srRelocHighLow`|Создает `reloc` для расположения, размер которого определяется указателем. Он преобразуется в BASED_HIGHLOW или BASED_DIR64 в зависимости от платформы.|  
|`srRelocHighAdj`|Создает `reloc` для старших 16 бит 32-разрядного числа, где 16 нижних бит включены в следующее слово в таблице. reloc.|  
|`srRelocMapToken`|Создает перемещение карт маркеров, отправляя в раздел. reloc значение Nothing.|  
|`srRelocRelative`|Указывает, что значением является адресная привязка относительных адресов.|  
|`srRelocFilePos`|Создает только относительный `reloc`раздела, отправляя в раздел. reloc значение Nothing. Этот `reloc` относится к расположению файла раздела, а не к виртуальному адресу раздела.|  
|`srRelocCodeRelative`|Указывает адресную привязку адреса, относительную для кода.|  
|`srRelocIA64Imm64`|Создает `reloc` для 64-разрядного адреса в инструкции `movl` IA64.|  
|`srRelocDir64`|Создает `reloc` для 64-разрядного адреса.|  
|`srRelocIA64PcRel25`|Создайте `reloc` для 25-разрядного адреса, относительного компьютера, в инструкции `br.call` IA64.|  
|`srRelocIA64PcRel64`|Создает `reloc` для 64-разрядного адреса, относительный для ПК, в инструкции `brl.call` IA64.|  
|`srRelocAbsoluteTagged`|Формирует 30-разрядную относительную `reloc`раздела, используемую для значений указателей с тегами.|  
|`srRelocSentinel`|Значение Sentinel, которое помогает гарантировать, что все дополнения к этому перечислению отражаются в массиве имен внутренних `reloc`.|  
|`srNoBaseReloc`|Указывает, что не следует выдавать базовый `reloc`.|  
|`srRelocPtr`|Значение, указывающее, что предварительная адресная привязка содержимого памяти является указателем, а не смещением раздела.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
