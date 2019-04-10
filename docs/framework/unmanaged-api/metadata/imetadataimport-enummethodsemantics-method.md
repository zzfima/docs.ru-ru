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
ms.openlocfilehash: 16cfa6df6251cd67860155cb8092e77a835eaaef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223274"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="6a9a9-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="6a9a9-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="6a9a9-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a9a9-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a9a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a9a9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6a9a9-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6a9a9-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="6a9a9-108">[in] Токен MethodDef, который ограничивает область перечисления.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="6a9a9-109">[out] Массив, используемый для хранения события или свойства.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6a9a9-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="6a9a9-111">[out] Количество событий или свойств, возвращаемых в `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a9a9-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6a9a9-112">Return Value</span></span>  
  
|<span data-ttu-id="6a9a9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a9a9-113">HRESULT</span></span>|<span data-ttu-id="6a9a9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6a9a9-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` <span data-ttu-id="6a9a9-115">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6a9a9-116">Отсутствуют события или свойства для перечисления.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="6a9a9-117">В этом случае `pcEventProp` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a9a9-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a9a9-118">Remarks</span></span>  
 <span data-ttu-id="6a9a9-119">Многие типами среды CLR определить *свойство* `Changed` события и `On` *свойство* `Changed` методы, связанные с их свойства.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="6a9a9-120">Например <xref:System.Windows.Forms.Control?displayProperty=nameWithType> определяет тип <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событий и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="6a9a9-121">Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> вызовах свойств <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который в свою очередь вызывает <xref:System.Windows.Forms.Control.FontChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="6a9a9-122">Можно вызвать `EnumMethodSemantics` с помощью MethodDef для <xref:System.Windows.Forms.Control.OnFontChanged%2A> для получения ссылок на <xref:System.Windows.Forms.Control.Font%2A> свойство и <xref:System.Windows.Forms.Control.FontChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="6a9a9-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a9a9-123">Требования</span><span class="sxs-lookup"><span data-stu-id="6a9a9-123">Requirements</span></span>  
 <span data-ttu-id="6a9a9-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a9a9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a9a9-125">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a9a9-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a9a9-126">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a9a9-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6a9a9-127">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6a9a9-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a9a9-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6a9a9-128">See also</span></span>

- [<span data-ttu-id="6a9a9-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6a9a9-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a9a9-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6a9a9-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
