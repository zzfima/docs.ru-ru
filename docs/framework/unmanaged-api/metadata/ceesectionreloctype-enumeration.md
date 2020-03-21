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
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="0678e-102">Перечисление CeeSectionRelocType</span><span class="sxs-lookup"><span data-stu-id="0678e-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="0678e-103">Предоставляет значения для влияния `reloc` на тип инструкции, излучаемые в вызове к [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="0678e-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0678e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0678e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0678e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0678e-105">Members</span></span>  
  
|<span data-ttu-id="0678e-106">Участник</span><span class="sxs-lookup"><span data-stu-id="0678e-106">Member</span></span>|<span data-ttu-id="0678e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0678e-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="0678e-108">Генерирует только раздел-родственник, `reloc`ничего не отправляя в раздел .reloc.</span><span class="sxs-lookup"><span data-stu-id="0678e-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="0678e-109">Генерирует `reloc` место для указателя.</span><span class="sxs-lookup"><span data-stu-id="0678e-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="0678e-110">Это превращается в BASED_HIGHLOW или BASED_DIR64 в зависимости от платформы.</span><span class="sxs-lookup"><span data-stu-id="0678e-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="0678e-111">Генерирует `reloc` для топ 16 битов 32-битного числа, где нижние 16 битов включены в следующее слово в таблице .reloc.</span><span class="sxs-lookup"><span data-stu-id="0678e-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="0678e-112">Генерирует перемещение токенов карты, ничего не отправляя в раздел .reloc.</span><span class="sxs-lookup"><span data-stu-id="0678e-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="0678e-113">Указывает, что значение является исправлением относительного адреса.</span><span class="sxs-lookup"><span data-stu-id="0678e-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="0678e-114">Генерирует только раздел-родственник, `reloc`ничего не отправляя в раздел .reloc.</span><span class="sxs-lookup"><span data-stu-id="0678e-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="0678e-115">Это `reloc` относительно положения файла раздела, а не виртуального адреса раздела.</span><span class="sxs-lookup"><span data-stu-id="0678e-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="0678e-116">Установить исправление код-относительного адреса.</span><span class="sxs-lookup"><span data-stu-id="0678e-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="0678e-117">Генерирует `reloc` 64-битный адрес в инструкции `movl` ia64.</span><span class="sxs-lookup"><span data-stu-id="0678e-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="0678e-118">Генерирует `reloc` 64-разрядный адрес.</span><span class="sxs-lookup"><span data-stu-id="0678e-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="0678e-119">Создайте `reloc` для 25-битного PC-относительного адреса `br.call` в инструкции ia64.</span><span class="sxs-lookup"><span data-stu-id="0678e-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="0678e-120">Генерирует `reloc` 64-разрядный pc-относительный адрес в инструкции ia64. `brl.call`</span><span class="sxs-lookup"><span data-stu-id="0678e-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="0678e-121">Генерирует 30-битный сечение-относительный, `reloc`используемый для помеченных значений указателя.</span><span class="sxs-lookup"><span data-stu-id="0678e-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="0678e-122">Значение дозорного, которое поможет обеспечить, чтобы любые `reloc` дополнения к этому эквайму были отражены во внутреннем массиве имен.</span><span class="sxs-lookup"><span data-stu-id="0678e-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="0678e-123">Указывает не излучать базу. `reloc`</span><span class="sxs-lookup"><span data-stu-id="0678e-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="0678e-124">Значение, указывающее на то, что предварительное исправление содержимого памяти является указателем, а не смещением секции.</span><span class="sxs-lookup"><span data-stu-id="0678e-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0678e-125">Требования</span><span class="sxs-lookup"><span data-stu-id="0678e-125">Requirements</span></span>  
 <span data-ttu-id="0678e-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0678e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0678e-127">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0678e-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0678e-128">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0678e-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0678e-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0678e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0678e-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0678e-130">See also</span></span>

- [<span data-ttu-id="0678e-131">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0678e-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="0678e-132">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="0678e-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="0678e-133">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="0678e-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
