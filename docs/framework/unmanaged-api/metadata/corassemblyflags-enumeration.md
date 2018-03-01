---
title: "Перечисление CorAssemblyFlags"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 059d896842c285bb071a25990ae9178c34ab802a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="ffe54-102">Перечисление CorAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="ffe54-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="ffe54-103">Содержит значения, которые описывают метаданные, применяемые к компиляции сборки.</span><span class="sxs-lookup"><span data-stu-id="ffe54-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffe54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffe54-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="ffe54-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ffe54-105">Members</span></span>  
  
|<span data-ttu-id="ffe54-106">Член</span><span class="sxs-lookup"><span data-stu-id="ffe54-106">Member</span></span>|<span data-ttu-id="ffe54-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="ffe54-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="ffe54-108">Указывает, что ссылка содержит полный, не хэшированный открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ffe54-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="ffe54-109">Указывает, что архитектура процессора не задана.</span><span class="sxs-lookup"><span data-stu-id="ffe54-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="ffe54-110">Указывает, что архитектура процессора нейтральный (PE32).</span><span class="sxs-lookup"><span data-stu-id="ffe54-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="ffe54-111">Указывает, что архитектура процессора — x86 (PE32).</span><span class="sxs-lookup"><span data-stu-id="ffe54-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="ffe54-112">Указывает архитектуру процессора Itanium (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="ffe54-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="ffe54-113">Указывает, что архитектура процессора — AMD X64 (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="ffe54-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="ffe54-114">Указывает архитектуру процессора ARM (PE32).</span><span class="sxs-lookup"><span data-stu-id="ffe54-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="ffe54-115">Указывает, что сборка является ссылочной сборкой; Это значит относится к любой архитектуры, но не может работать на любой архитектуры.</span><span class="sxs-lookup"><span data-stu-id="ffe54-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="ffe54-116">Таким образом, флаг совпадает со значением `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="ffe54-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="ffe54-117">Указывает, что флаги архитектуры процессора должны распространяться на `AssemblyRef` запись.</span><span class="sxs-lookup"><span data-stu-id="ffe54-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="ffe54-118">Маска, описывающая архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="ffe54-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="ffe54-119">Указывает, что включено описание архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="ffe54-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="ffe54-120">Указывает число смещений во флагах архитектуры процессора и из индекса.</span><span class="sxs-lookup"><span data-stu-id="ffe54-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="ffe54-121">Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffe54-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="ffe54-122">Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffe54-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="ffe54-123">Указывает, что сборки могут быть перенаправлены во время выполнения на сборку из другого издателя.</span><span class="sxs-lookup"><span data-stu-id="ffe54-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="ffe54-124">Маска, которая описывает тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="ffe54-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="ffe54-125">Указывает тип содержимого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ffe54-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="ffe54-126">Указывает [!INCLUDE[wrt](../../../../includes/wrt-md.md)] тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="ffe54-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffe54-127">Требования</span><span class="sxs-lookup"><span data-stu-id="ffe54-127">Requirements</span></span>  
 <span data-ttu-id="ffe54-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffe54-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe54-129">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ffe54-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ffe54-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe54-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe54-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ffe54-131">See Also</span></span>  
 [<span data-ttu-id="ffe54-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ffe54-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
