---
title: "Перечисление CeeSectionRelocType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocType
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocType
helpviewer_keywords: CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d257778a9a05e2654d7f91c0205424d001f5ae3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionreloctype-enumeration"></a>Перечисление CeeSectionRelocType
Предоставляет значения для влияния на тип `reloc` инструкции в вызове [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
|Член|Описание:|  
|------------|-----------------|  
|`srRelocAbsolute`|Создает только раздел относительно `reloc`отправляют nothing в раздел .reloc.|  
|`srRelocHighLow`|Приводит к возникновению ошибки `reloc` расположения размером указателя. Этот запрос преобразуется в BASED_HIGHLOW или BASED_DIR64 в зависимости от платформы.|  
|`srRelocHighAdj`|Приводит к возникновению ошибки `reloc` первые 16 бит 32-разрядное число, когда младшие 16 бит включаются в следующее слово в таблице .reloc.|  
|`srRelocMapToken`|Создает перемещение сопоставления маркера, отправляя в раздел .reloc значение nothing.|  
|`srRelocRelative`|Указывает, что значение является относительной адресной привязкой.|  
|`srRelocFilePos`|Создает только раздел относительно `reloc`отправляют nothing в раздел .reloc. Это `reloc` относительно позиции файла данного раздела, а не виртуального адреса этого раздела.|  
|`srRelocCodeRelative`|Задает адресную привязку относительно кода.|  
|`srRelocIA64Imm64`|Приводит к возникновению ошибки `reloc` для 64-разрядного адреса в ia64 `movl` инструкции.|  
|`srRelocDir64`|Приводит к возникновению ошибки `reloc` для 64-разрядного адреса.|  
|`srRelocIA64PcRel25`|Создание `reloc` для 25-разрядного адреса относительно ПК в ia64 `br.call` инструкции.|  
|`srRelocIA64PcRel64`|Приводит к возникновению ошибки `reloc` для 64-разрядного адреса относительно ПК в ia64 `brl.call` инструкции.|  
|`srRelocAbsoluteTagged`|Создает раздел относительно 30-разрядного `reloc`, используемой для значений указателей с тегами.|  
|`srRelocSentinel`|Контрольного значения для обеспечения любые добавления к этому перечислению, отражаются на встроенную `reloc` имя массива.|  
|`srNoBaseReloc`|Указывает не для создания базового `reloc`.|  
|`srRelocPtr`|Значение, указывающее, что содержимое предварительной адресной привязки памяти является указателем, а не раздела смещение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [Интерфейс ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
