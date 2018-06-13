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
ms.openlocfilehash: 82b81ec29dece182548ead046edc7cb754fbf00e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430665"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="92376-102">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="92376-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="92376-103">Указывает на эквивалентность два идентификатора сборки, что определяется [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="92376-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92376-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92376-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="92376-105">Участники</span><span class="sxs-lookup"><span data-stu-id="92376-105">Members</span></span>  
  
|<span data-ttu-id="92376-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="92376-106">Member name</span></span>|<span data-ttu-id="92376-107">Описание</span><span class="sxs-lookup"><span data-stu-id="92376-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="92376-108">Указывает, что все поля сборки совпали при сравнении.</span><span class="sxs-lookup"><span data-stu-id="92376-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="92376-109">Указывает, что сборки эквивалентны на основе общих языка среды выполнения (CLR) версии унификации для номеров версии сборок в платформе .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="92376-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="92376-110">Указывает частичное совпадение сборок на основе унификации среды CLR для номеров версии сборок в платформе .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="92376-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="92376-111">Указывает частичное совпадение сборок.</span><span class="sxs-lookup"><span data-stu-id="92376-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="92376-112">Указывает частичное совпадение сборок на основе унификации прежних версий для номеров версии.</span><span class="sxs-lookup"><span data-stu-id="92376-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="92376-113">Указывает частичное совпадение сборок с простыми именами.</span><span class="sxs-lookup"><span data-stu-id="92376-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="92376-114">Указывает, что сборки эквивалентны на основе унификации CLR номеров версии прежних версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92376-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="92376-115">Указывает соответствие между двумя сборками простым именем, чьи номера версии были пропущены.</span><span class="sxs-lookup"><span data-stu-id="92376-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="92376-116">Указывает, что соответствие между двумя сборками.</span><span class="sxs-lookup"><span data-stu-id="92376-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="92376-117">Указывает, что две сборки соответствуют за исключением номеров версии, которые совпадают только частично.</span><span class="sxs-lookup"><span data-stu-id="92376-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="92376-118">Указывает, что две сборки соответствуют за исключением номеров версии, которые не совпадают.</span><span class="sxs-lookup"><span data-stu-id="92376-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="92376-119">Указывает, что причина неравенства не известна.</span><span class="sxs-lookup"><span data-stu-id="92376-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92376-120">Требования</span><span class="sxs-lookup"><span data-stu-id="92376-120">Requirements</span></span>  
 <span data-ttu-id="92376-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92376-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92376-122">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="92376-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="92376-123">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92376-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92376-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92376-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92376-125">См. также</span><span class="sxs-lookup"><span data-stu-id="92376-125">See Also</span></span>  
 [<span data-ttu-id="92376-126">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="92376-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [<span data-ttu-id="92376-127">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="92376-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
