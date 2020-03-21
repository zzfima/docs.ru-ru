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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175464"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="bfa68-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="bfa68-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="bfa68-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="bfa68-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa68-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfa68-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfa68-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfa68-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bfa68-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="bfa68-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bfa68-107">Это должно быть NULL для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="bfa68-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="bfa68-108">(в) Токен MethodDef, ограничивающий область перечисления.</span><span class="sxs-lookup"><span data-stu-id="bfa68-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="bfa68-109">(ваут) Массив, используемый для хранения событий или свойств.</span><span class="sxs-lookup"><span data-stu-id="bfa68-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bfa68-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="bfa68-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="bfa68-111">(ваут) Количество событий или свойств, `rEventProp`возвращенных в .</span><span class="sxs-lookup"><span data-stu-id="bfa68-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfa68-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfa68-112">Return Value</span></span>  
  
|<span data-ttu-id="bfa68-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfa68-113">HRESULT</span></span>|<span data-ttu-id="bfa68-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bfa68-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bfa68-115">`EnumMethodSemantics`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="bfa68-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bfa68-116">Нет событий или свойств, которые можно перечислить.</span><span class="sxs-lookup"><span data-stu-id="bfa68-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="bfa68-117">В этом `pcEventProp` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="bfa68-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfa68-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="bfa68-118">Remarks</span></span>  
 <span data-ttu-id="bfa68-119">Многие общие типы времени выполнения `On`языка определяют события *свойств* `Changed` и методы *свойств,* `Changed` связанные с их свойствами.</span><span class="sxs-lookup"><span data-stu-id="bfa68-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="bfa68-120">Например, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> тип определяет <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событие и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="bfa68-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="bfa68-121">Метод набора доступа <xref:System.Windows.Forms.Control.Font%2A> метода <xref:System.Windows.Forms.Control.OnFontChanged%2A> вызовов свойств, который, в свою очередь, поднимает <xref:System.Windows.Forms.Control.FontChanged> событие.</span><span class="sxs-lookup"><span data-stu-id="bfa68-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="bfa68-122">Вы бы `EnumMethodSemantics` позвонить с <xref:System.Windows.Forms.Control.OnFontChanged%2A> помощью MethodDef <xref:System.Windows.Forms.Control.Font%2A> для <xref:System.Windows.Forms.Control.FontChanged> получения ссылок на имущество и событие.</span><span class="sxs-lookup"><span data-stu-id="bfa68-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa68-123">Требования</span><span class="sxs-lookup"><span data-stu-id="bfa68-123">Requirements</span></span>  
 <span data-ttu-id="bfa68-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa68-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa68-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bfa68-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bfa68-126">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfa68-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bfa68-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa68-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa68-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bfa68-128">See also</span></span>

- [<span data-ttu-id="bfa68-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bfa68-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bfa68-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bfa68-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
