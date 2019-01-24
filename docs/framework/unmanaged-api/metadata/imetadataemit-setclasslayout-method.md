---
title: Метод IMetaDataEmit::SetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dc1664551683066a33fb52e16e4909506601f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588695"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="a7096-102">Метод IMetaDataEmit::SetClassLayout</span><span class="sxs-lookup"><span data-stu-id="a7096-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="a7096-103">Макет полей для класса, который был определен во время предыдущего вызова для завершения [метод DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="a7096-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7096-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7096-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7096-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7096-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a7096-106">[in] `mdTypeDef` Токен, который указывает класс располагаться.</span><span class="sxs-lookup"><span data-stu-id="a7096-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="a7096-107">[in] Упаковочный размер: 1, 2, 4, 8 или 16 байт.</span><span class="sxs-lookup"><span data-stu-id="a7096-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="a7096-108">Упаковочный размер равен число байтов между смежными полями.</span><span class="sxs-lookup"><span data-stu-id="a7096-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="a7096-109">[in] Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) структуры, каждый из которых указывает, что поля класса и смещение в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="a7096-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="a7096-110">Массива с `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="a7096-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="a7096-111">[in] Размер в байтах, класса.</span><span class="sxs-lookup"><span data-stu-id="a7096-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7096-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7096-112">Remarks</span></span>  
 <span data-ttu-id="a7096-113">Класс изначально определяется путем вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) метод и задавая один из трех структур поля класса: Авто, последовательный или явной.</span><span class="sxs-lookup"><span data-stu-id="a7096-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="a7096-114">Как правило необходимо использование автоматической разметки и позволить среде выполнения выбрать лучший способ расположения полей.</span><span class="sxs-lookup"><span data-stu-id="a7096-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="a7096-115">Тем не менее может потребоваться поля, располагались в порядке их использования неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="a7096-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="a7096-116">В этом случае выберите либо последовательный или явный макет и вызов `SetClassLayout` для завершения макета полей:</span><span class="sxs-lookup"><span data-stu-id="a7096-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="a7096-117">Последовательное размещение: Укажите размер пакета.</span><span class="sxs-lookup"><span data-stu-id="a7096-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="a7096-118">Поле выравнивается в соответствии с его естественному размеру или упаковочный размер, что приводит меньшего размера смещение поля.</span><span class="sxs-lookup"><span data-stu-id="a7096-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="a7096-119">Задайте `rFieldOffsets` и `ulClassSize` до нуля.</span><span class="sxs-lookup"><span data-stu-id="a7096-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="a7096-120">Явное размещение: Задайте смещение каждого поля или размер класса, а также размером уплотнения.</span><span class="sxs-lookup"><span data-stu-id="a7096-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7096-121">Требования</span><span class="sxs-lookup"><span data-stu-id="a7096-121">Requirements</span></span>  
 <span data-ttu-id="a7096-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7096-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7096-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7096-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7096-124">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7096-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7096-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7096-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7096-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a7096-126">See also</span></span>
- [<span data-ttu-id="a7096-127">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a7096-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a7096-128">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a7096-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
