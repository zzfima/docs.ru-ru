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
ms.openlocfilehash: 15fd75ae807ee5cd7f94f6e650639c3be0628429
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136543"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="339a8-102">Метод IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="339a8-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="339a8-103">Задает функции PInvoke подписи метода, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="339a8-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="339a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="339a8-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="339a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="339a8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="339a8-106">[in] Маркер целевого метода.</span><span class="sxs-lookup"><span data-stu-id="339a8-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="339a8-107">[in] Флаги, используемые PInvoke для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="339a8-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="339a8-108">[in] Имя целевого объекта метод export в неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="339a8-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="339a8-109">[in] Маркер для целевого DLL в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="339a8-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="339a8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="339a8-110">Requirements</span></span>  
 <span data-ttu-id="339a8-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="339a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="339a8-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="339a8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="339a8-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="339a8-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="339a8-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="339a8-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="339a8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="339a8-115">See also</span></span>

- [<span data-ttu-id="339a8-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="339a8-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="339a8-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="339a8-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
