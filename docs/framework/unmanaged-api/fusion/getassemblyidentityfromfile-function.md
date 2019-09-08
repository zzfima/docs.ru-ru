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
ms.openlocfilehash: 2657ac619bb86bc200de9ce229bf82e4339f78d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796292"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="295dc-102">Функция GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="295dc-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="295dc-103">Возвращает указатель на `IUnknown` объект с указанным `IID` в сборке по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="295dc-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="295dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="295dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="295dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="295dc-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="295dc-106">окне Допустимый путь к запрошенной сборке.</span><span class="sxs-lookup"><span data-stu-id="295dc-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="295dc-107">окне `IID` Возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="295dc-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="295dc-108">заполняет Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="295dc-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="295dc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="295dc-109">Requirements</span></span>  
 <span data-ttu-id="295dc-110">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="295dc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="295dc-111">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="295dc-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="295dc-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="295dc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295dc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="295dc-113">See also</span></span>

- [<span data-ttu-id="295dc-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="295dc-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="295dc-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="295dc-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
