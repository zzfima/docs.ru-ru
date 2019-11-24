---
title: Метод IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: ff6932b6040a19e0ccda2f8d2140fa131cdd9224
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450074"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="a0b5c-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="a0b5c-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="a0b5c-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0b5c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0b5c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a0b5c-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a0b5c-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="a0b5c-108">[in] A MethodDef token that limits the scope of the enumeration.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="a0b5c-109">[out] The array used to store the events or properties.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a0b5c-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="a0b5c-111">[out] The number of events or properties returned in `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0b5c-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0b5c-112">Return Value</span></span>  
  
|<span data-ttu-id="a0b5c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0b5c-113">HRESULT</span></span>|<span data-ttu-id="a0b5c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a0b5c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a0b5c-115">`EnumMethodSemantics` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a0b5c-116">There are no events or properties to enumerate.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="a0b5c-117">In that case, `pcEventProp` is zero.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0b5c-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="a0b5c-118">Remarks</span></span>  
 <span data-ttu-id="a0b5c-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="a0b5c-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="a0b5c-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="a0b5c-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span><span class="sxs-lookup"><span data-stu-id="a0b5c-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b5c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="a0b5c-123">Requirements</span></span>  
 <span data-ttu-id="a0b5c-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0b5c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b5c-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0b5c-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0b5c-126">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0b5c-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0b5c-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b5c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b5c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a0b5c-128">See also</span></span>

- [<span data-ttu-id="a0b5c-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a0b5c-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a0b5c-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a0b5c-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
