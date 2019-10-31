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
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123071"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="62198-102">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="62198-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="62198-103">Возвращает значение, указывающее, является ли указанная сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="62198-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62198-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62198-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="62198-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62198-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="62198-106">окне Имя проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="62198-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="62198-107">заполняет Логическое значение, указывающее, является ли сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="62198-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="62198-108">окне Неканоническая строка, содержащая уникальный идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="62198-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="62198-109">[входной] Размер `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="62198-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62198-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="62198-110">Remarks</span></span>  
 <span data-ttu-id="62198-111">Параметр `pwzAssemblyReference` — это указатель на символьную строку, содержащую имя сборки.</span><span class="sxs-lookup"><span data-stu-id="62198-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="62198-112">Если эта сборка является частью .NET Framework, параметр `pbIsFrameworkAssembly` будет содержать логическое значение `true`.</span><span class="sxs-lookup"><span data-stu-id="62198-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="62198-113">Если именованная сборка не является частью .NET Framework или если параметр `pwzAssemblyReference` не имеет имени сборки, `pbIsFrameworkAssembly` будет содержать логическое значение `false`.</span><span class="sxs-lookup"><span data-stu-id="62198-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62198-114">Требования</span><span class="sxs-lookup"><span data-stu-id="62198-114">Requirements</span></span>  
 <span data-ttu-id="62198-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62198-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62198-116">См. также</span><span class="sxs-lookup"><span data-stu-id="62198-116">See also</span></span>

- [<span data-ttu-id="62198-117">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="62198-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
