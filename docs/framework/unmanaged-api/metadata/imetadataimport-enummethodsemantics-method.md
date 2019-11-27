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
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="32a0c-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="32a0c-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="32a0c-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="32a0c-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32a0c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32a0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32a0c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="32a0c-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="32a0c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="32a0c-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="32a0c-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="32a0c-108">окне Токен MethodDef, ограничивающий область перечисления.</span><span class="sxs-lookup"><span data-stu-id="32a0c-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="32a0c-109">заполняет Массив, используемый для хранения событий или свойств.</span><span class="sxs-lookup"><span data-stu-id="32a0c-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="32a0c-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="32a0c-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="32a0c-111">заполняет Количество событий или свойств, возвращаемых в `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="32a0c-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32a0c-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32a0c-112">Return Value</span></span>  
  
|<span data-ttu-id="32a0c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32a0c-113">HRESULT</span></span>|<span data-ttu-id="32a0c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="32a0c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="32a0c-115">`EnumMethodSemantics` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="32a0c-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="32a0c-116">Нет событий или свойств для перечисления.</span><span class="sxs-lookup"><span data-stu-id="32a0c-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="32a0c-117">В этом случае `pcEventProp` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="32a0c-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32a0c-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="32a0c-118">Remarks</span></span>  
 <span data-ttu-id="32a0c-119">Многие типы среды CLR определяют события`Changed` *свойств* и `On`*свойства*`Changed` методы, связанные с их свойствами.</span><span class="sxs-lookup"><span data-stu-id="32a0c-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="32a0c-120">Например, тип <xref:System.Windows.Forms.Control?displayProperty=nameWithType> определяет свойство <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.FontChanged> событие и метод <xref:System.Windows.Forms.Control.OnFontChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="32a0c-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="32a0c-121">Метод доступа set свойства <xref:System.Windows.Forms.Control.Font%2A> вызывает метод <xref:System.Windows.Forms.Control.OnFontChanged%2A>, который, в свою очередь, вызывает событие <xref:System.Windows.Forms.Control.FontChanged>.</span><span class="sxs-lookup"><span data-stu-id="32a0c-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="32a0c-122">Можно вызвать `EnumMethodSemantics` с помощью MethodDef для <xref:System.Windows.Forms.Control.OnFontChanged%2A>, чтобы получить ссылки на свойство <xref:System.Windows.Forms.Control.Font%2A> и на событие <xref:System.Windows.Forms.Control.FontChanged>.</span><span class="sxs-lookup"><span data-stu-id="32a0c-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32a0c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="32a0c-123">Requirements</span></span>  
 <span data-ttu-id="32a0c-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32a0c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32a0c-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="32a0c-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32a0c-126">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="32a0c-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32a0c-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32a0c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a0c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="32a0c-128">See also</span></span>

- [<span data-ttu-id="32a0c-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="32a0c-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="32a0c-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="32a0c-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
