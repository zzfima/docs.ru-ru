---
title: Функция IsFrameworkAssembly
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 989d046bba1ba3170649e9d908a850bd1177fdd2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773829"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="5ec5a-102">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="5ec5a-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="5ec5a-103">Получает значение, указывающее, управляется ли указанная сборка.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ec5a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ec5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ec5a-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="5ec5a-106">[in] Имя сборки.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="5ec5a-107">[out] Логическое значение, указывающее, управляется ли сборка.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="5ec5a-108">[in] Это uncanonicalized строка, содержащая уникальный идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="5ec5a-109">[входной] Размер `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ec5a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ec5a-110">Remarks</span></span>  
 <span data-ttu-id="5ec5a-111">`pwzAssemblyReference` Параметр является указателем на строку символов, содержащая имя сборки.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="5ec5a-112">Если эта сборка является частью .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать значение типа Boolean `true`.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="5ec5a-113">Если для этого именованную сборку не является частью платформы .NET Framework или `pwzAssemblyReference` параметр не задает имя сборки, `pbIsFrameworkAssembly` будет содержать значение типа Boolean `false`.</span><span class="sxs-lookup"><span data-stu-id="5ec5a-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec5a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5ec5a-114">Requirements</span></span>  
 <span data-ttu-id="5ec5a-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ec5a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec5a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5ec5a-116">See also</span></span>

- [<span data-ttu-id="5ec5a-117">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="5ec5a-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
