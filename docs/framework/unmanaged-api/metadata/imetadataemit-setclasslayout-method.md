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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177561"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="feb78-102">Метод IMetaDataEmit::SetClassLayout</span><span class="sxs-lookup"><span data-stu-id="feb78-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="feb78-103">Завершает расположение полей для класса, определяемого предыдущим вызовом в [метод DefineTypeDef.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)</span><span class="sxs-lookup"><span data-stu-id="feb78-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="feb78-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="feb78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="feb78-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="feb78-106">(в) Токен, `mdTypeDef` опоедающие класс, который должен быть выложен.</span><span class="sxs-lookup"><span data-stu-id="feb78-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="feb78-107">(в) Размер упаковки: 1, 2, 4, 8 или 16 байтов.</span><span class="sxs-lookup"><span data-stu-id="feb78-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="feb78-108">Размер упаковки — это количество байтов между смежными полями.</span><span class="sxs-lookup"><span data-stu-id="feb78-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="feb78-109">(в) Массив [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) структур, каждая из которых определяет поле класса и смещение поля в классе.</span><span class="sxs-lookup"><span data-stu-id="feb78-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="feb78-110">Упраздните `mdTokenNil`массив с помощью .</span><span class="sxs-lookup"><span data-stu-id="feb78-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="feb78-111">(в) Размер, в байтах, класса.</span><span class="sxs-lookup"><span data-stu-id="feb78-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feb78-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="feb78-112">Remarks</span></span>  
 <span data-ttu-id="feb78-113">Класс первоначально определяется путем вызова метода [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) и указания одного из трех макетов для полей класса: автоматического, последовательного или явного.</span><span class="sxs-lookup"><span data-stu-id="feb78-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="feb78-114">Как правило, вы будете использовать автоматический макет и позволить времени выполнения выбрать лучший способ выложить поля.</span><span class="sxs-lookup"><span data-stu-id="feb78-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="feb78-115">Однако, возможно, вы захотите, чтобы поля были выложены в соответствии с расположением, которое использует неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="feb78-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="feb78-116">В этом случае выберите либо последовательный, либо `SetClassLayout` явный макет и позвоните для завершения макета полей:</span><span class="sxs-lookup"><span data-stu-id="feb78-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="feb78-117">Последовательная компоновка: Укажите размер упаковки.</span><span class="sxs-lookup"><span data-stu-id="feb78-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="feb78-118">Поле выравнивается либо в зависимости от его естественного размера или размера упаковки, в зависимости от того, что приводит к меньшему смещению поля.</span><span class="sxs-lookup"><span data-stu-id="feb78-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="feb78-119">`rFieldOffsets` Установить `ulClassSize` и к нулю.</span><span class="sxs-lookup"><span data-stu-id="feb78-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="feb78-120">Явная компоновка: либо укажите смещение каждого поля, либо укажите размер класса и размер упаковки.</span><span class="sxs-lookup"><span data-stu-id="feb78-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feb78-121">Требования</span><span class="sxs-lookup"><span data-stu-id="feb78-121">Requirements</span></span>  
 <span data-ttu-id="feb78-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feb78-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feb78-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="feb78-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="feb78-124">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="feb78-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="feb78-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feb78-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb78-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="feb78-126">See also</span></span>

- [<span data-ttu-id="feb78-127">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="feb78-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="feb78-128">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="feb78-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
