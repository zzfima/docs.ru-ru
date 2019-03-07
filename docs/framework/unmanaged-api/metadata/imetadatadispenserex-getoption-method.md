---
title: Метод IMetaDataDispenserEx::GetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5512c503d8b4048c613ab88c2b4d9d19cdbb9dca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479038"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="1a224-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="1a224-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="1a224-103">Получает значение указанного параметра в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="1a224-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="1a224-104">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="1a224-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a224-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a224-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a224-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a224-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="1a224-107">[in] Указатель на идентификатор GUID, который задает параметр, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="1a224-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="1a224-108">См. в разделе "Примечания" для получения списка поддерживаемых идентификаторов GUID.</span><span class="sxs-lookup"><span data-stu-id="1a224-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="1a224-109">[out] Значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="1a224-109">[out] The value of the returned option.</span></span> <span data-ttu-id="1a224-110">Тип этого значения будет вариант указанного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="1a224-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a224-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a224-111">Remarks</span></span>  
 <span data-ttu-id="1a224-112">Ниже приведены идентификаторы GUID, которые поддерживаются для этого метода.</span><span class="sxs-lookup"><span data-stu-id="1a224-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="1a224-113">Описание, см. в разделе [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="1a224-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="1a224-114">Если `optionId` находится не в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG`, указывающее, неверный параметр.</span><span class="sxs-lookup"><span data-stu-id="1a224-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="1a224-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="1a224-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="1a224-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="1a224-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="1a224-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="1a224-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="1a224-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="1a224-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="1a224-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="1a224-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="1a224-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="1a224-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="1a224-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="1a224-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a224-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1a224-122">Requirements</span></span>  
 <span data-ttu-id="1a224-123">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a224-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a224-124">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a224-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a224-125">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a224-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a224-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a224-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a224-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1a224-127">See also</span></span>
- [<span data-ttu-id="1a224-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="1a224-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="1a224-129">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="1a224-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
