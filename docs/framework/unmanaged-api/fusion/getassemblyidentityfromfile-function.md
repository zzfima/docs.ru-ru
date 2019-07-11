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
ms.openlocfilehash: 581c675cfb69503e6366471a469ffed1a2d13b1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745228"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="5a291-102">Функция GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="5a291-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="5a291-103">Возвращает указатель на `IUnknown` объект с указанным `IID` в сборку по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="5a291-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a291-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a291-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a291-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a291-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="5a291-106">[in] Допустимый путь к запрошенной сборке.</span><span class="sxs-lookup"><span data-stu-id="5a291-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="5a291-107">[in] `IID` Интерфейса для возврата.</span><span class="sxs-lookup"><span data-stu-id="5a291-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="5a291-108">[out] Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5a291-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a291-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5a291-109">Requirements</span></span>  
 <span data-ttu-id="5a291-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a291-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a291-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5a291-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5a291-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a291-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a291-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5a291-113">See also</span></span>

- [<span data-ttu-id="5a291-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="5a291-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="5a291-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="5a291-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
