---
title: Метод IMetaDataEmit::DefinePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 343f4f3cb88f98d1952e2910255d6cceb0cf0cc6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483371"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="c2a28-102">Метод IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="c2a28-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="c2a28-103">Задает функции PInvoke подписи метода, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="c2a28-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2a28-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2a28-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c2a28-106">[in] Маркер целевого метода.</span><span class="sxs-lookup"><span data-stu-id="c2a28-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="c2a28-107">[in] Флаги, используемые PInvoke для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="c2a28-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="c2a28-108">[in] Имя целевого объекта метод export в неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="c2a28-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="c2a28-109">[in] Маркер для целевого DLL в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="c2a28-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a28-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c2a28-110">Requirements</span></span>  
 <span data-ttu-id="c2a28-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a28-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a28-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2a28-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2a28-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2a28-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2a28-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a28-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a28-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c2a28-115">See also</span></span>
- [<span data-ttu-id="c2a28-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c2a28-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c2a28-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c2a28-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
