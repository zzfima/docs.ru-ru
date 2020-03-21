---
title: Метод IMetaDataEmit::SetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: fe0b4b7fef0d05c4acc06dad5bc8a4eaf0722c9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175581"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="12236-102">Метод IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="12236-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="12236-103">Устанавливает относительный виртуальный адрес указанного метода.</span><span class="sxs-lookup"><span data-stu-id="12236-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12236-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12236-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12236-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12236-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="12236-106">(в) Токен для реализации целевого метода или метода.</span><span class="sxs-lookup"><span data-stu-id="12236-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="12236-107">(в) Адрес кода или области данных.</span><span class="sxs-lookup"><span data-stu-id="12236-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12236-108">Требования</span><span class="sxs-lookup"><span data-stu-id="12236-108">Requirements</span></span>  
 <span data-ttu-id="12236-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12236-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12236-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12236-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12236-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12236-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12236-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12236-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12236-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12236-113">See also</span></span>

- [<span data-ttu-id="12236-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="12236-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="12236-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="12236-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
