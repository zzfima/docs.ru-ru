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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072718"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="03ead-102">Перечисление CorAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="03ead-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="03ead-103">Содержит значения, которые описывают метаданные, применяемые к компиляции сборки.</span><span class="sxs-lookup"><span data-stu-id="03ead-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ead-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03ead-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="03ead-105">Участники</span><span class="sxs-lookup"><span data-stu-id="03ead-105">Members</span></span>  
  
|<span data-ttu-id="03ead-106">Член</span><span class="sxs-lookup"><span data-stu-id="03ead-106">Member</span></span>|<span data-ttu-id="03ead-107">Описание</span><span class="sxs-lookup"><span data-stu-id="03ead-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="03ead-108">Указывает, что ссылки на сборку содержит полный, не хэшированный открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="03ead-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="03ead-109">Указывает, что архитектура процессора не определен.</span><span class="sxs-lookup"><span data-stu-id="03ead-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="03ead-110">Указывает, что архитектура процессора является нейтральный (PE32).</span><span class="sxs-lookup"><span data-stu-id="03ead-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="03ead-111">Указывает архитектуру процессора x86 (PE32).</span><span class="sxs-lookup"><span data-stu-id="03ead-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="03ead-112">Указывает архитектуру процессора Itanium (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="03ead-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="03ead-113">Указывает архитектуру процессора AMD X64 (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="03ead-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="03ead-114">Указывает архитектуру процессора ARM (PE32).</span><span class="sxs-lookup"><span data-stu-id="03ead-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="03ead-115">Указывает, что сборка является ссылочной сборки; то есть применяется к любой архитектуры, но не могут работать на компьютерах с любой архитектурой.</span><span class="sxs-lookup"><span data-stu-id="03ead-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="03ead-116">Таким образом, флаг совпадает со значением `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="03ead-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="03ead-117">Указывает, что флаги архитектуры процессора должны распространяться на `AssemblyRef` записи.</span><span class="sxs-lookup"><span data-stu-id="03ead-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="03ead-118">Маска, которая описывает архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="03ead-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="03ead-119">Указывает, что включено описание архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="03ead-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="03ead-120">Указывает число смещений во флагах архитектуры процессора и из индекса.</span><span class="sxs-lookup"><span data-stu-id="03ead-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="03ead-121">Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="03ead-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="03ead-122">Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="03ead-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="03ead-123">Указывает, что сборка может быть перенацелена во время выполнения на сборку от другого издателя.</span><span class="sxs-lookup"><span data-stu-id="03ead-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="03ead-124">Маска, которая описывает тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="03ead-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="03ead-125">Указывает тип содержимого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="03ead-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="03ead-126">Указывает [!INCLUDE[wrt](../../../../includes/wrt-md.md)] тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="03ead-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03ead-127">Требования</span><span class="sxs-lookup"><span data-stu-id="03ead-127">Requirements</span></span>  
 <span data-ttu-id="03ead-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03ead-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ead-129">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="03ead-129">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="03ead-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="03ead-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="03ead-131">См. также</span><span class="sxs-lookup"><span data-stu-id="03ead-131">See also</span></span>

- [<span data-ttu-id="03ead-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="03ead-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
