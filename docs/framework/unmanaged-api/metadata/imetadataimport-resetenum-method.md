---
title: Метод IMetaDataImport::ResetEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 3dd82588cf2dbf92fdda66fd7674c17ddc8b7306
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177190"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="5919e-102">Метод IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="5919e-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="5919e-103">Возвращает заданный перечислитель в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="5919e-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5919e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5919e-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5919e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5919e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="5919e-106">(в) Регистратор для сбросить.</span><span class="sxs-lookup"><span data-stu-id="5919e-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="5919e-107">(в) Новая позиция, на которой можно разместить регистратор.</span><span class="sxs-lookup"><span data-stu-id="5919e-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5919e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5919e-108">Requirements</span></span>  
 <span data-ttu-id="5919e-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5919e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5919e-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5919e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5919e-111">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5919e-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5919e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5919e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5919e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5919e-113">See also</span></span>

- [<span data-ttu-id="5919e-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5919e-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5919e-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5919e-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
