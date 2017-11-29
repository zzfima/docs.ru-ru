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
ms.openlocfilehash: fa9db222c81c2d6536b782c3e047e24c773bd018
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="a0a3a-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="a0a3a-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="a0a3a-103">Возвращает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="a0a3a-104">Параметр определяет способ обработки вызовов текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a3a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0a3a-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0a3a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0a3a-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="a0a3a-107">[in] Указатель на идентификатор GUID, который указывает параметр, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="a0a3a-108">Список поддерживаемых идентификаторов GUID см.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a0a3a-109">[out] Значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-109">[out] The value of the returned option.</span></span> <span data-ttu-id="a0a3a-110">Тип этого значения будет разновидностью указанного параметра.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0a3a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0a3a-111">Remarks</span></span>  
 <span data-ttu-id="a0a3a-112">Ниже приведены идентификаторы GUID, которые поддерживаются для данного метода.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="a0a3a-113">Описание приведено в разделе [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="a0a3a-114">Если `optionId` находится не в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG`, указывающее, неверный параметр.</span><span class="sxs-lookup"><span data-stu-id="a0a3a-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="a0a3a-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="a0a3a-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="a0a3a-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="a0a3a-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="a0a3a-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="a0a3a-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="a0a3a-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="a0a3a-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="a0a3a-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="a0a3a-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="a0a3a-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="a0a3a-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="a0a3a-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="a0a3a-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a3a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a0a3a-122">Requirements</span></span>  
 <span data-ttu-id="a0a3a-123">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0a3a-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a3a-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0a3a-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0a3a-125">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0a3a-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0a3a-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a3a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a3a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a0a3a-127">See Also</span></span>  
 [<span data-ttu-id="a0a3a-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="a0a3a-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="a0a3a-129">IMetaDataDispenser-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a0a3a-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
