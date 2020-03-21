---
title: Метод IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175594"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="b2935-102">Метод IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="b2935-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="b2935-103">Устанавливает или изменяет функции подписи PInvoke метода, как это определено предыдущим вызовом на [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="b2935-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2935-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2935-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2935-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2935-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b2935-106">(в) К `mdToken` которой применяется информация о картографии.</span><span class="sxs-lookup"><span data-stu-id="b2935-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="b2935-107">(в) Флаги, используемые PInvoke для отображения.</span><span class="sxs-lookup"><span data-stu-id="b2935-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="b2935-108">Это битмаска ценностей. `CorPinvokeMap`</span><span class="sxs-lookup"><span data-stu-id="b2935-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="b2935-109">(в) Название целевого экспорта в родном DLL.</span><span class="sxs-lookup"><span data-stu-id="b2935-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="b2935-110">(в) Токен `mdModuleRef` для цели неуправляемый DLL.</span><span class="sxs-lookup"><span data-stu-id="b2935-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2935-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b2935-111">Requirements</span></span>  
 <span data-ttu-id="b2935-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2935-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2935-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2935-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2935-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2935-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2935-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2935-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2935-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b2935-116">See also</span></span>

- [<span data-ttu-id="b2935-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b2935-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b2935-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b2935-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
