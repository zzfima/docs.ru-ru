---
title: "Перечисления Fusion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], fusion
- fusion enumerations [.NET Framework]
- enumerations [.NET Framework fusion]
ms.assetid: 5817b4bc-b0ba-4b2f-a11c-a03dd8cb8f84
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f136f98758dc7162ec26323391e0c1295a8444f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="fusion-enumerations"></a><span data-ttu-id="627cd-102">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="627cd-102">Fusion Enumerations</span></span>
<span data-ttu-id="627cd-103">В этом разделе описываются неуправляемые перечисления, используемые API Fusion.</span><span class="sxs-lookup"><span data-stu-id="627cd-103">This section describes the unmanaged enumerations that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="627cd-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="627cd-104">In This Section</span></span>  
 [<span data-ttu-id="627cd-105">Перечисление ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="627cd-105">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 <span data-ttu-id="627cd-106">Указывает источник сборки, представленной [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="627cd-106">Indicates the source of an assembly represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="627cd-107">Перечисление ASM_CMP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="627cd-107">ASM_CMP_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md)  
 <span data-ttu-id="627cd-108">Указывает версию, сборки, язык и региональные параметры, подпись и две сборки для сравнения с [IAssemblyName::IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="627cd-108">Indicates the version, build, culture, signature, and so on, of two assemblies to be compared by the [IAssemblyName::IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) method.</span></span>  
  
 [<span data-ttu-id="627cd-109">Перечисление ASM_DISPLAY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="627cd-109">ASM_DISPLAY_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md)  
 <span data-ttu-id="627cd-110">Указывает версию, сборки, язык и региональные параметры, подпись и сборки, отображаемое имя будет использоваться [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="627cd-110">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) method.</span></span>  
  
 [<span data-ttu-id="627cd-111">Перечисление ASM_NAME</span><span class="sxs-lookup"><span data-stu-id="627cd-111">ASM_NAME Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-name-enumeration.md)  
 <span data-ttu-id="627cd-112">Указывает версию, сборки, язык и региональные параметры, подпись и сборка, свойства которого будут извлечены или заданы [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) методы.</span><span class="sxs-lookup"><span data-stu-id="627cd-112">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) methods.</span></span>  
  
 [<span data-ttu-id="627cd-113">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="627cd-113">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)  
 <span data-ttu-id="627cd-114">Указывает на эквивалентность два идентификатора сборки, что определяется [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="627cd-114">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
 [<span data-ttu-id="627cd-115">Перечисление CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="627cd-115">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/create-asm-name-obj-flags-enumeration.md)  
 <span data-ttu-id="627cd-116">Задает атрибуты `IAssemblyName` объекта при построении с [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="627cd-116">Specifies the attributes of an `IAssemblyName` object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="627cd-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="627cd-117">Related Sections</span></span>  
 [<span data-ttu-id="627cd-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="627cd-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [<span data-ttu-id="627cd-119">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="627cd-119">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="627cd-120">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="627cd-120">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
