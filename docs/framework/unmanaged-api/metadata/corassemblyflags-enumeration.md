---
title: Перечисление CorAssemblyFlags
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
ms.openlocfilehash: fda890cee5f513ea8cf7e82e710f5451a860c49f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443908"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="5e28c-102">Перечисление CorAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="5e28c-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="5e28c-103">Содержит значения, которые описывают метаданные, применяемые к компиляции сборки.</span><span class="sxs-lookup"><span data-stu-id="5e28c-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e28c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e28c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5e28c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="5e28c-105">Members</span></span>  
  
|<span data-ttu-id="5e28c-106">Член</span><span class="sxs-lookup"><span data-stu-id="5e28c-106">Member</span></span>|<span data-ttu-id="5e28c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5e28c-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="5e28c-108">Указывает, что ссылка на сборку содержит полный, нехэшированный открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="5e28c-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="5e28c-109">Указывает, что архитектура процессора не определена.</span><span class="sxs-lookup"><span data-stu-id="5e28c-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="5e28c-110">Указывает, что архитектура процессора нейтральна (формат PE32).</span><span class="sxs-lookup"><span data-stu-id="5e28c-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="5e28c-111">Указывает, что архитектура процессора — x86 (формат PE32).</span><span class="sxs-lookup"><span data-stu-id="5e28c-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="5e28c-112">Указывает, что архитектура процессора — Itanium (формат PE32 +).</span><span class="sxs-lookup"><span data-stu-id="5e28c-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="5e28c-113">Указывает, что архитектура процессора — это AMD x64 (формат PE32 +).</span><span class="sxs-lookup"><span data-stu-id="5e28c-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="5e28c-114">Указывает, что архитектура процессора — ARM (формат PE32).</span><span class="sxs-lookup"><span data-stu-id="5e28c-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="5e28c-115">Указывает, что сборка является ссылочной сборкой; то есть он применяется к любой архитектуре, но не может работать в любой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="5e28c-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="5e28c-116">Таким образом, флаг будет таким же, как `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="5e28c-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="5e28c-117">Указывает, что флаги архитектуры процессора должны распространяться на запись `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="5e28c-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="5e28c-118">Маска, описывающая архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="5e28c-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="5e28c-119">Указывает, что включено описание архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="5e28c-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="5e28c-120">Указывает число смещений в флагах архитектуры процессора в индекс и из него.</span><span class="sxs-lookup"><span data-stu-id="5e28c-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="5e28c-121">Указывает соответствующее значение из <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5e28c-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="5e28c-122">Указывает соответствующее значение из <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5e28c-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="5e28c-123">Указывает, что сборка может быть перенацелена во время выполнения в сборку из другого издателя.</span><span class="sxs-lookup"><span data-stu-id="5e28c-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="5e28c-124">Маска, описывающая тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="5e28c-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="5e28c-125">Указывает тип содержимого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e28c-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="5e28c-126">Указывает тип содержимого среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="5e28c-126">Indicates the Windows Runtime content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e28c-127">Требования</span><span class="sxs-lookup"><span data-stu-id="5e28c-127">Requirements</span></span>  
 <span data-ttu-id="5e28c-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e28c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e28c-129">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="5e28c-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5e28c-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e28c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e28c-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e28c-131">See also</span></span>

- [<span data-ttu-id="5e28c-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="5e28c-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
