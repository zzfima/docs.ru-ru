---
title: "Функция IsFrameworkAssembly"
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
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa077ce13031772ec2ea20708c1dbd29da02d32a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="9964c-102">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="9964c-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="9964c-103">Возвращает значение, указывающее, является ли указанная сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="9964c-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9964c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9964c-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9964c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9964c-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="9964c-106">[in] Имя сборки для проверки.</span><span class="sxs-lookup"><span data-stu-id="9964c-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="9964c-107">[out] Логическое значение, указывающее, управляется ли сборки.</span><span class="sxs-lookup"><span data-stu-id="9964c-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="9964c-108">[in] Uncanonicalized строка, которая содержит уникальный идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="9964c-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="9964c-109">[входной] Размер `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="9964c-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9964c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9964c-110">Remarks</span></span>  
 <span data-ttu-id="9964c-111">`pwzAssemblyReference` Параметр является указателем на строку символов, содержащая имя сборки.</span><span class="sxs-lookup"><span data-stu-id="9964c-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="9964c-112">Если эта сборка является частью платформы .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать значение типа Boolean `true`.</span><span class="sxs-lookup"><span data-stu-id="9964c-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="9964c-113">Если для этого именованную сборку не является частью .NET Framework или `pwzAssemblyReference` параметр не задает имя сборки, `pbIsFrameworkAssembly` будет содержать значение типа Boolean `false`.</span><span class="sxs-lookup"><span data-stu-id="9964c-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9964c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9964c-114">Requirements</span></span>  
 <span data-ttu-id="9964c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9964c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9964c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9964c-116">See Also</span></span>  
 [<span data-ttu-id="9964c-117">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="9964c-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
