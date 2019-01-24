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
ms.openlocfilehash: 6287b7adf0ef6f6269a51f608657444f5fa7f74e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580230"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="74ce5-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="74ce5-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="74ce5-103">Получает значение указанного параметра в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="74ce5-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="74ce5-104">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="74ce5-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ce5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74ce5-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74ce5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="74ce5-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="74ce5-107">[in] Указатель на идентификатор GUID, который задает параметр, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="74ce5-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="74ce5-108">См. в разделе "Примечания" для получения списка поддерживаемых идентификаторов GUID.</span><span class="sxs-lookup"><span data-stu-id="74ce5-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="74ce5-109">[out] Значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="74ce5-109">[out] The value of the returned option.</span></span> <span data-ttu-id="74ce5-110">Тип этого значения будет вариант указанного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="74ce5-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74ce5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="74ce5-111">Remarks</span></span>  
 <span data-ttu-id="74ce5-112">Ниже приведены идентификаторы GUID, которые поддерживаются для этого метода.</span><span class="sxs-lookup"><span data-stu-id="74ce5-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="74ce5-113">Описание, см. в разделе [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="74ce5-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="74ce5-114">Если `optionId` находится не в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG`, указывающее, неверный параметр.</span><span class="sxs-lookup"><span data-stu-id="74ce5-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="74ce5-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="74ce5-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="74ce5-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="74ce5-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="74ce5-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="74ce5-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="74ce5-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="74ce5-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="74ce5-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="74ce5-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="74ce5-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="74ce5-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="74ce5-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="74ce5-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74ce5-122">Требования</span><span class="sxs-lookup"><span data-stu-id="74ce5-122">Requirements</span></span>  
 <span data-ttu-id="74ce5-123">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74ce5-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74ce5-124">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74ce5-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74ce5-125">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74ce5-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74ce5-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74ce5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ce5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="74ce5-127">See also</span></span>
- [<span data-ttu-id="74ce5-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="74ce5-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="74ce5-129">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="74ce5-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
