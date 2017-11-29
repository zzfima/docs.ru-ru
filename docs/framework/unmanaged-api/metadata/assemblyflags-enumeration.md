---
title: "Перечисление AssemblyFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91760b6d16b663257bf3d89915da3bd88b3411bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="6a426-102">Перечисление AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="6a426-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="6a426-103">Содержит значения, описывающие функции времени выполнения сборки.</span><span class="sxs-lookup"><span data-stu-id="6a426-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a426-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a426-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6a426-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6a426-105">Members</span></span>  
  
|<span data-ttu-id="6a426-106">Член</span><span class="sxs-lookup"><span data-stu-id="6a426-106">Member</span></span>|<span data-ttu-id="6a426-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6a426-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="6a426-108">Указывает, что определения экспортируемого типа неявные внутри файлов, которые составляют сборку.</span><span class="sxs-lookup"><span data-stu-id="6a426-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="6a426-109">В .NET Framework версий 1.0 и 1.1 это значение всегда является предполагается заданы.</span><span class="sxs-lookup"><span data-stu-id="6a426-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="6a426-110">Указывает, что определения ресурсов неявное внутри файлов, которые составляют сборку.</span><span class="sxs-lookup"><span data-stu-id="6a426-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="6a426-111">В .NET Framework 1.0 и 1.1 это значение всегда предполагается требуется задать.</span><span class="sxs-lookup"><span data-stu-id="6a426-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="6a426-112">Указывает, что сборка не может выполняться с другими своими версиями, если они выполняются в том же домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6a426-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="6a426-113">Указывает, что сборка не может выполняться с другими своими версиями, если они выполняются в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="6a426-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="6a426-114">Указывает, что сборка не может выполняться с другими своими версиями, если они выполняются на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="6a426-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a426-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a426-115">Remarks</span></span>  
 <span data-ttu-id="6a426-116">Значения между 0x0010 и 0x0070, включительно, используются для описания функций обеспечения совместимости side-by-side по ссылке сборки.</span><span class="sxs-lookup"><span data-stu-id="6a426-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="6a426-117">Если ни одно из этих значений задаются сборки предполагается side-by-side-совместимыми.</span><span class="sxs-lookup"><span data-stu-id="6a426-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a426-118">Требования</span><span class="sxs-lookup"><span data-stu-id="6a426-118">Requirements</span></span>  
 <span data-ttu-id="6a426-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a426-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a426-120">**Заголовок:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a426-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="6a426-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a426-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a426-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a426-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a426-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6a426-123">See Also</span></span>  
 [<span data-ttu-id="6a426-124">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="6a426-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="6a426-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="6a426-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
