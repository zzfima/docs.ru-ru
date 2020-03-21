---
title: Метод IMetaDataEmit::SetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: 1037cd4210605192870d43d88979b89af6536380
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175659"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="37166-102">Метод IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="37166-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="37166-103">Устанавливает информацию о маршализах PInvoke для поля, возврата метода или параметра метода, на который ссылается указанный маркер.</span><span class="sxs-lookup"><span data-stu-id="37166-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37166-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37166-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37166-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37166-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="37166-106">(в) Токен для элемента целевого данных.</span><span class="sxs-lookup"><span data-stu-id="37166-106">[in] The token for target data item.</span></span> <span data-ttu-id="37166-107">Это либо `mdFieldDef` знак, `mdParamDef` либо жетон.</span><span class="sxs-lookup"><span data-stu-id="37166-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="37166-108">(в) Подпись для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="37166-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="37166-109">(в) Количество байтов `pvNativeType`в .</span><span class="sxs-lookup"><span data-stu-id="37166-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37166-110">Требования</span><span class="sxs-lookup"><span data-stu-id="37166-110">Requirements</span></span>  
 <span data-ttu-id="37166-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37166-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37166-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37166-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37166-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37166-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37166-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37166-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37166-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="37166-115">See also</span></span>

- [<span data-ttu-id="37166-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="37166-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="37166-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="37166-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
