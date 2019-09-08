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
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796314"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="2e5a9-102">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="2e5a9-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="2e5a9-103">Возвращает значение, указывающее, является ли указанная сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e5a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e5a9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e5a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e5a9-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="2e5a9-106">окне Имя проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="2e5a9-107">заполняет Логическое значение, указывающее, является ли сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="2e5a9-108">окне Неканоническая строка, содержащая уникальный идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="2e5a9-109">[входной] Размер `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e5a9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e5a9-110">Remarks</span></span>  
 <span data-ttu-id="2e5a9-111">`pwzAssemblyReference` Параметр является указателем на символьную строку, содержащую имя сборки.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="2e5a9-112">Если эта сборка является частью .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать логическое `true`значение.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="2e5a9-113">Если именованная сборка не является частью .NET Framework или если `pwzAssemblyReference` параметр не имеет имени сборки, `pbIsFrameworkAssembly` то будет `false`содержать логическое значение.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e5a9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="2e5a9-114">Requirements</span></span>  
 <span data-ttu-id="2e5a9-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e5a9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e5a9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2e5a9-116">See also</span></span>

- [<span data-ttu-id="2e5a9-117">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="2e5a9-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
