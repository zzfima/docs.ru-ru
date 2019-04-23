---
title: Функция CreateAssemblyCache
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf78ded62f11b336d9f5fe0f3a205275ae37189b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157408"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="ae99b-102">Функция CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="ae99b-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="ae99b-103">Возвращает указатель на новый [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) экземпляр, представляющий глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="ae99b-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae99b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae99b-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae99b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae99b-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="ae99b-106">[out] Возвращенный `IAssemblyCache` указатель.</span><span class="sxs-lookup"><span data-stu-id="ae99b-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="ae99b-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="ae99b-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ae99b-108">`dwReserved` должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="ae99b-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae99b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ae99b-109">Requirements</span></span>  
 <span data-ttu-id="ae99b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae99b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae99b-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ae99b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ae99b-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae99b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae99b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae99b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae99b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ae99b-114">See also</span></span>

- [<span data-ttu-id="ae99b-115">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="ae99b-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="ae99b-116">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="ae99b-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="ae99b-117">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="ae99b-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
