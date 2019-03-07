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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6021cd0126f4dd85b796a3110cd95a83c0f77ff4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466795"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="c5e5a-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="c5e5a-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="c5e5a-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5e5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5e5a-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5e5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5e5a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c5e5a-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c5e5a-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="c5e5a-108">[in] Токен MethodDef, который ограничивает область перечисления.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="c5e5a-109">[out] Массив, используемый для хранения события или свойства.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c5e5a-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="c5e5a-111">[out] Количество событий или свойств, возвращаемых в `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5e5a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5e5a-112">Return Value</span></span>  
  
|<span data-ttu-id="c5e5a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5e5a-113">HRESULT</span></span>|<span data-ttu-id="c5e5a-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="c5e5a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c5e5a-115">`EnumMethodSemantics` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c5e5a-116">Отсутствуют события или свойства для перечисления.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="c5e5a-117">В этом случае `pcEventProp` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5e5a-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5e5a-118">Remarks</span></span>  
 <span data-ttu-id="c5e5a-119">Многие типами среды CLR определить *свойство* `Changed` события и `On` *свойство* `Changed` методы, связанные с их свойства.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="c5e5a-120">Например <xref:System.Windows.Forms.Control?displayProperty=nameWithType> определяет тип <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событий и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="c5e5a-121">Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> вызовах свойств <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который в свою очередь вызывает <xref:System.Windows.Forms.Control.FontChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="c5e5a-122">Можно вызвать `EnumMethodSemantics` с помощью MethodDef для <xref:System.Windows.Forms.Control.OnFontChanged%2A> для получения ссылок на <xref:System.Windows.Forms.Control.Font%2A> свойство и <xref:System.Windows.Forms.Control.FontChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="c5e5a-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5e5a-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c5e5a-123">Requirements</span></span>  
 <span data-ttu-id="c5e5a-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5e5a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5e5a-125">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5e5a-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5e5a-126">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5e5a-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5e5a-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5e5a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e5a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c5e5a-128">See also</span></span>
- [<span data-ttu-id="c5e5a-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c5e5a-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c5e5a-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c5e5a-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
