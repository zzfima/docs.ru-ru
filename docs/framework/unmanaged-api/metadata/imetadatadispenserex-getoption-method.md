---
title: "Метод IMetaDataDispenserEx::GetOption"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fd59fa20e95de8486eaa7f18a63333459361ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="d86eb-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="d86eb-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="d86eb-103">Возвращает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="d86eb-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="d86eb-104">Параметр определяет способ обработки вызовов текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="d86eb-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d86eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d86eb-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d86eb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d86eb-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="d86eb-107">[in] Указатель на идентификатор GUID, который указывает параметр, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="d86eb-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="d86eb-108">Список поддерживаемых идентификаторов GUID см.</span><span class="sxs-lookup"><span data-stu-id="d86eb-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d86eb-109">[out] Значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="d86eb-109">[out] The value of the returned option.</span></span> <span data-ttu-id="d86eb-110">Тип этого значения будет разновидностью указанного параметра.</span><span class="sxs-lookup"><span data-stu-id="d86eb-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d86eb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d86eb-111">Remarks</span></span>  
 <span data-ttu-id="d86eb-112">Ниже приведены идентификаторы GUID, которые поддерживаются для данного метода.</span><span class="sxs-lookup"><span data-stu-id="d86eb-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="d86eb-113">Описание приведено в разделе [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d86eb-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="d86eb-114">Если `optionId` находится не в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG`, указывающее, неверный параметр.</span><span class="sxs-lookup"><span data-stu-id="d86eb-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="d86eb-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="d86eb-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="d86eb-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="d86eb-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="d86eb-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="d86eb-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="d86eb-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="d86eb-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="d86eb-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="d86eb-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="d86eb-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="d86eb-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="d86eb-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="d86eb-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d86eb-122">Требования</span><span class="sxs-lookup"><span data-stu-id="d86eb-122">Requirements</span></span>  
 <span data-ttu-id="d86eb-123">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d86eb-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d86eb-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d86eb-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d86eb-125">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d86eb-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d86eb-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d86eb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86eb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d86eb-127">See Also</span></span>  
 [<span data-ttu-id="d86eb-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d86eb-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="d86eb-129">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="d86eb-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
