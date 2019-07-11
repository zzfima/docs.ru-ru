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
ms.openlocfilehash: a0f6b38cefa1c9b36a660559c1d97fc88f7dbddc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777752"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="61977-102">Метод IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="61977-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="61977-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="61977-103">This method is not implemented.</span></span> <span data-ttu-id="61977-104">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="61977-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61977-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61977-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="61977-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="61977-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="61977-107">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="61977-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="61977-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="61977-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="61977-109">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="61977-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="61977-110">[in] Имя модуля.</span><span class="sxs-lookup"><span data-stu-id="61977-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="61977-111">[in] Сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="61977-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="61977-112">[out] Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="61977-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="61977-113">[in] Размер в байтах из `szName`.</span><span class="sxs-lookup"><span data-stu-id="61977-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="61977-114">[out] Число символов, фактически возвращенных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="61977-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61977-115">Требования</span><span class="sxs-lookup"><span data-stu-id="61977-115">Requirements</span></span>  
 <span data-ttu-id="61977-116">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61977-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61977-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61977-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61977-118">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61977-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61977-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61977-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61977-120">См. также</span><span class="sxs-lookup"><span data-stu-id="61977-120">See also</span></span>

- [<span data-ttu-id="61977-121">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="61977-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="61977-122">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="61977-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
