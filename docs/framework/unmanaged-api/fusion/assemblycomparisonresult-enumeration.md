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
ms.openlocfilehash: 3d3fd88a2c1ac90f823b23d8d2bcb5b177a625c3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109009"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="59d58-102">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="59d58-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="59d58-103">Указывает эквивалентность двух удостоверений сборки, как определено функцией [компареассемблидентити](compareassemblyidentity-function.md) .</span><span class="sxs-lookup"><span data-stu-id="59d58-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59d58-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59d58-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="59d58-105">Члены</span><span class="sxs-lookup"><span data-stu-id="59d58-105">Members</span></span>  
  
|<span data-ttu-id="59d58-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="59d58-106">Member name</span></span>|<span data-ttu-id="59d58-107">Описание</span><span class="sxs-lookup"><span data-stu-id="59d58-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="59d58-108">Указывает, что все поля сборки в совпадении сравнения.</span><span class="sxs-lookup"><span data-stu-id="59d58-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="59d58-109">Указывает, что сборки считаются эквивалентными на основе унификации номеров версий сборки среды CLR в версии .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="59d58-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="59d58-110">Указывает частичное совпадение сборок на основе унификации версий сборки CLR в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="59d58-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="59d58-111">Указывает частичное совпадение сборок.</span><span class="sxs-lookup"><span data-stu-id="59d58-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="59d58-112">Указывает частичное совпадение сборок на основе унификации устаревших номеров версий.</span><span class="sxs-lookup"><span data-stu-id="59d58-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="59d58-113">Указывает частичное совпадение с простыми именованными сборками.</span><span class="sxs-lookup"><span data-stu-id="59d58-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="59d58-114">Указывает, что сборки считаются эквивалентными на основе унификации версии CLR номеров версий в устаревших версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59d58-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="59d58-115">Указывает соответствие между двумя простыми именованными сборками, Номера версий которых были пропущены.</span><span class="sxs-lookup"><span data-stu-id="59d58-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="59d58-116">Указывает, что между двумя сборками не произошло совпадений.</span><span class="sxs-lookup"><span data-stu-id="59d58-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="59d58-117">Указывает, что две сборки совпадают, за исключением номеров версий, которые соответствуют только частично.</span><span class="sxs-lookup"><span data-stu-id="59d58-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="59d58-118">Указывает, что две сборки совпадают, за исключением номеров версий, которые не совпадают.</span><span class="sxs-lookup"><span data-stu-id="59d58-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="59d58-119">Указывает, что причина неравенства неизвестна.</span><span class="sxs-lookup"><span data-stu-id="59d58-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59d58-120">Требования</span><span class="sxs-lookup"><span data-stu-id="59d58-120">Requirements</span></span>  
 <span data-ttu-id="59d58-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59d58-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59d58-122">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="59d58-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="59d58-123">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59d58-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59d58-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59d58-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d58-125">См. также</span><span class="sxs-lookup"><span data-stu-id="59d58-125">See also</span></span>

- [<span data-ttu-id="59d58-126">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="59d58-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="59d58-127">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="59d58-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
