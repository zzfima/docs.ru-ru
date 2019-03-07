---
title: Метод IMetaDataDispenserEx::FindAssemblyModule
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ccb6331399ef3479e43bdb9dc4a72b5fd196672c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495346"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="63387-102">Метод IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="63387-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="63387-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="63387-103">This method is not implemented.</span></span> <span data-ttu-id="63387-104">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="63387-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63387-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63387-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63387-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="63387-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="63387-107">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="63387-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="63387-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="63387-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="63387-109">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="63387-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="63387-110">[in] Имя модуля.</span><span class="sxs-lookup"><span data-stu-id="63387-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="63387-111">[in] Сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="63387-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="63387-112">[out] Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="63387-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="63387-113">[in] Размер в байтах из `szName`.</span><span class="sxs-lookup"><span data-stu-id="63387-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="63387-114">[out] Число символов, фактически возвращенных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="63387-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63387-115">Требования</span><span class="sxs-lookup"><span data-stu-id="63387-115">Requirements</span></span>  
 <span data-ttu-id="63387-116">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63387-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63387-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="63387-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63387-118">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63387-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63387-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63387-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63387-120">См. также</span><span class="sxs-lookup"><span data-stu-id="63387-120">See also</span></span>
- [<span data-ttu-id="63387-121">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="63387-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="63387-122">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="63387-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
