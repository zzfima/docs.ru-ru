---
title: Перечисление AssemblyComparisonResult
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b8ecc996e14263510e2d0a658cec020696c263
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141704"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="4c192-102">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="4c192-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="4c192-103">Эквивалентность двух идентификаторов сборок, указывает, что определяется [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="4c192-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c192-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c192-104">Syntax</span></span>  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="4c192-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4c192-105">Members</span></span>  
  
|<span data-ttu-id="4c192-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="4c192-106">Member name</span></span>|<span data-ttu-id="4c192-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4c192-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="4c192-108">Указывает, что все поля сборки в соответствие сравнения.</span><span class="sxs-lookup"><span data-stu-id="4c192-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="4c192-109">Указывает, что сборки эквивалентны на основе общих унификации версию (CLR) среды выполнения языка для номеров версии сборок в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="4c192-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="4c192-110">Указывает на частичное совпадение сборок на основе унификации среды CLR для номеров версии сборок в .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="4c192-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="4c192-111">Указывает на частичное совпадение сборок.</span><span class="sxs-lookup"><span data-stu-id="4c192-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="4c192-112">Указывает на частичное совпадение сборок, на основе предыдущих версий унификации для номера версий.</span><span class="sxs-lookup"><span data-stu-id="4c192-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="4c192-113">Указывает на частичное совпадение простым именем сборки.</span><span class="sxs-lookup"><span data-stu-id="4c192-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="4c192-114">Указывает, что сборки эквивалентны на основе унификации CLR для номера версий в прежних версиях платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c192-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="4c192-115">Указывает соответствие между две простым именем сборки, номера версий были пропущены.</span><span class="sxs-lookup"><span data-stu-id="4c192-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="4c192-116">Указывает, что совершенно не совпадают две сборки.</span><span class="sxs-lookup"><span data-stu-id="4c192-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="4c192-117">Указывает совпадение двух сборок, за исключением номеров версии, которые соответствуют только частично.</span><span class="sxs-lookup"><span data-stu-id="4c192-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="4c192-118">Указывает совпадение двух сборок, за исключением номеров версии, которые не совпадают.</span><span class="sxs-lookup"><span data-stu-id="4c192-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="4c192-119">Указывает, что причина неравенства не известна.</span><span class="sxs-lookup"><span data-stu-id="4c192-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c192-120">Требования</span><span class="sxs-lookup"><span data-stu-id="4c192-120">Requirements</span></span>  
 <span data-ttu-id="4c192-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c192-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c192-122">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4c192-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4c192-123">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c192-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="4c192-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4c192-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4c192-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4c192-125">See also</span></span>

- [<span data-ttu-id="4c192-126">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="4c192-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [<span data-ttu-id="4c192-127">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="4c192-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
