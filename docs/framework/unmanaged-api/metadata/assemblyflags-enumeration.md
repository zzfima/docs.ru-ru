---
title: Перечисление AssemblyFlags
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c86a4fd2788c8ea2df5d9e54c5c221afd179704
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091425"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="91e3d-102">Перечисление AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="91e3d-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="91e3d-103">Содержит значения, описывающие возможности времени выполнения сборки.</span><span class="sxs-lookup"><span data-stu-id="91e3d-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91e3d-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="91e3d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="91e3d-105">Members</span></span>  
  
|<span data-ttu-id="91e3d-106">Член</span><span class="sxs-lookup"><span data-stu-id="91e3d-106">Member</span></span>|<span data-ttu-id="91e3d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="91e3d-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="91e3d-108">Указывает, что экспортированный тип определения являются неявными внутри файлов, составляющих сборку.</span><span class="sxs-lookup"><span data-stu-id="91e3d-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="91e3d-109">В .NET Framework версий 1.0 и 1.1 это значение всегда считается задать.</span><span class="sxs-lookup"><span data-stu-id="91e3d-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="91e3d-110">Указывает, что определения ресурсов являются неявными внутри файлов, составляющих сборку.</span><span class="sxs-lookup"><span data-stu-id="91e3d-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="91e3d-111">В .NET Framework 1.0 и 1.1 это значение всегда считается задать.</span><span class="sxs-lookup"><span data-stu-id="91e3d-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="91e3d-112">Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="91e3d-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="91e3d-113">Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="91e3d-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="91e3d-114">Указывает, что сборка не может выполняться с другими версиями, если они выполняются на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="91e3d-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91e3d-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="91e3d-115">Remarks</span></span>  
 <span data-ttu-id="91e3d-116">Значения между 0x0010 и 0x0070, включительно, используются для описания функции обеспечения совместимости side-by-side по ссылке сборки.</span><span class="sxs-lookup"><span data-stu-id="91e3d-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="91e3d-117">Если ни одно из этих значений, предполагается, что сборки side-by-side-совместимыми.</span><span class="sxs-lookup"><span data-stu-id="91e3d-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91e3d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="91e3d-118">Requirements</span></span>  
 <span data-ttu-id="91e3d-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91e3d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91e3d-120">**Заголовок.** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91e3d-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="91e3d-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91e3d-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91e3d-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91e3d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e3d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="91e3d-123">See also</span></span>

- [<span data-ttu-id="91e3d-124">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="91e3d-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="91e3d-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="91e3d-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
