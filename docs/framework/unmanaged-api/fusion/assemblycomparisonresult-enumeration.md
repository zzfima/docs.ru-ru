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
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178294"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="c5bb0-102">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="c5bb0-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="c5bb0-103">Указывает эквивалентность двух идентификаторов сборки, определяемых функцией [CompareAssemblyIdentity.](compareassemblyidentity-function.md)</span><span class="sxs-lookup"><span data-stu-id="c5bb0-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bb0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5bb0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c5bb0-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c5bb0-105">Members</span></span>  
  
|<span data-ttu-id="c5bb0-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="c5bb0-106">Member name</span></span>|<span data-ttu-id="c5bb0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c5bb0-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="c5bb0-108">Означает, что все поля сборки в сравнении.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="c5bb0-109">Указывается, что сборки считаются эквивалентными на основе общей версии выполнения языка (CLR) унификации номеров сборочной версии в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="c5bb0-110">Указывает частичное совпадение сборок на основе объединения номеров сборочной версии CLR в .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="c5bb0-111">Указывает частичное совпадение сборок.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="c5bb0-112">Указывает частичное совпадение сборок на основе устаревшего объединения номеров версий.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="c5bb0-113">Указывает частичное совпадение просто названных сборок.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="c5bb0-114">Указывает, что сборки считаются эквивалентными на основе объединения номеров версий CLR в устаревших версиях рамочной программы .NET.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="c5bb0-115">Указывает на совпадение между двумя просто названными сборками, номера версий которых были проигнорированы.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="c5bb0-116">Указывает на то, что между двумя сборками не произошло совпадений.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="c5bb0-117">Означает, что две сборки совпадают, за исключением их номеров версий, которые совпадают лишь частично.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="c5bb0-118">Означает, что две сборки совпадают, за исключением их номеров версий, которые не совпадают.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="c5bb0-119">Указывает на то, что причина неэквивалентности неизвестна.</span><span class="sxs-lookup"><span data-stu-id="c5bb0-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5bb0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c5bb0-120">Requirements</span></span>  
 <span data-ttu-id="c5bb0-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5bb0-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5bb0-122">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c5bb0-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c5bb0-123">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5bb0-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5bb0-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5bb0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bb0-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c5bb0-125">See also</span></span>

- [<span data-ttu-id="c5bb0-126">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="c5bb0-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="c5bb0-127">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="c5bb0-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
