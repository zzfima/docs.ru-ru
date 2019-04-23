---
title: Функция GetAssemblyIdentityFromFile
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f5dd25ec2a6a1b0b5d6266c3d8e728bd128a9ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106318"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="cd30d-102">Функция GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="cd30d-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="cd30d-103">Возвращает указатель на `IUnknown` объект с указанным `IID` в сборку по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="cd30d-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd30d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd30d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd30d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd30d-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="cd30d-106">[in] Допустимый путь к запрошенной сборке.</span><span class="sxs-lookup"><span data-stu-id="cd30d-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="cd30d-107">[in] `IID` Интерфейса для возврата.</span><span class="sxs-lookup"><span data-stu-id="cd30d-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="cd30d-108">[out] Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cd30d-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd30d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cd30d-109">Requirements</span></span>  
 <span data-ttu-id="cd30d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd30d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd30d-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="cd30d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cd30d-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd30d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd30d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cd30d-113">See also</span></span>

- [<span data-ttu-id="cd30d-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="cd30d-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="cd30d-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="cd30d-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
