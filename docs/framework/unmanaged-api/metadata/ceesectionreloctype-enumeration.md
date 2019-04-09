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
ms.openlocfilehash: 882242da493c49a2e6aa09888e9503dcf2933589
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119591"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="0e129-102">Перечисление CeeSectionRelocType</span><span class="sxs-lookup"><span data-stu-id="0e129-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="0e129-103">Предоставляет значения для влияния на тип `reloc` инструкции в вызове [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="0e129-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e129-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e129-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0e129-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0e129-105">Members</span></span>  
  
|<span data-ttu-id="0e129-106">Член</span><span class="sxs-lookup"><span data-stu-id="0e129-106">Member</span></span>|<span data-ttu-id="0e129-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0e129-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="0e129-108">Создает только раздел относительно `reloc`отправляют ничего в раздел .reloc.</span><span class="sxs-lookup"><span data-stu-id="0e129-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="0e129-109">Создает `reloc` для расположения размера указателя.</span><span class="sxs-lookup"><span data-stu-id="0e129-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="0e129-110">Это преобразуется в BASED_HIGHLOW или BASED_DIR64 зависимости от платформы.</span><span class="sxs-lookup"><span data-stu-id="0e129-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="0e129-111">Создает `reloc` для старших 16 бит 32-разрядное число, в котором младшие 16 бит, включаются в следующего слова в таблице .reloc.</span><span class="sxs-lookup"><span data-stu-id="0e129-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="0e129-112">Создает перемещение сопоставления маркера, отправляя в раздел .reloc значение nothing.</span><span class="sxs-lookup"><span data-stu-id="0e129-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="0e129-113">Указывает, что значение является относительной адресной привязкой.</span><span class="sxs-lookup"><span data-stu-id="0e129-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="0e129-114">Создает только раздел относительно `reloc`отправляют ничего в раздел .reloc.</span><span class="sxs-lookup"><span data-stu-id="0e129-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="0e129-115">Это `reloc` относительно позиции файла данного раздела, а не виртуального адреса этого раздела.</span><span class="sxs-lookup"><span data-stu-id="0e129-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="0e129-116">Указывает адрес относительно кода адресной привязки.</span><span class="sxs-lookup"><span data-stu-id="0e129-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="0e129-117">Создает `reloc` для 64-разрядные адреса в ia64 `movl` инструкции.</span><span class="sxs-lookup"><span data-stu-id="0e129-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="0e129-118">Создает `reloc` для 64-разрядный адрес.</span><span class="sxs-lookup"><span data-stu-id="0e129-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="0e129-119">Создать `reloc` для 25-разрядного адреса относительно ПК в ia64 `br.call` инструкции.</span><span class="sxs-lookup"><span data-stu-id="0e129-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="0e129-120">Создает `reloc` для 64-разрядный адрес относительно ПК в ia64 `brl.call` инструкции.</span><span class="sxs-lookup"><span data-stu-id="0e129-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="0e129-121">Создает раздел относительно 30-разрядного `reloc`, которое используется для значений указателей с тегами.</span><span class="sxs-lookup"><span data-stu-id="0e129-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="0e129-122">Значение-Метка для обеспечения любые дополнения для этого перечисления отражаются к внутреннему `reloc` в массиве имен.</span><span class="sxs-lookup"><span data-stu-id="0e129-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="0e129-123">Указывает не выдавать базового `reloc`.</span><span class="sxs-lookup"><span data-stu-id="0e129-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="0e129-124">Значение, указывающее, что содержимое предварительной адресной привязки памяти является указателем, а не раздела смещение.</span><span class="sxs-lookup"><span data-stu-id="0e129-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e129-125">Требования</span><span class="sxs-lookup"><span data-stu-id="0e129-125">Requirements</span></span>  
 <span data-ttu-id="0e129-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e129-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e129-127">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0e129-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e129-128">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e129-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0e129-129">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0e129-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0e129-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0e129-130">See also</span></span>

- [<span data-ttu-id="0e129-131">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0e129-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="0e129-132">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="0e129-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="0e129-133">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="0e129-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
