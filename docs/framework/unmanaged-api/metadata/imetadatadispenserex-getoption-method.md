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
ms.openlocfilehash: fe9bc9aea4ceb0f5b5c03416f43894b482c3294e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044295"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="3da6e-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="3da6e-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="3da6e-103">Получает значение указанного параметра в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="3da6e-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="3da6e-104">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="3da6e-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da6e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3da6e-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3da6e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3da6e-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="3da6e-107">[in] Указатель на идентификатор GUID, который задает параметр, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="3da6e-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="3da6e-108">См. в разделе "Примечания" для получения списка поддерживаемых идентификаторов GUID.</span><span class="sxs-lookup"><span data-stu-id="3da6e-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3da6e-109">[out] Значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="3da6e-109">[out] The value of the returned option.</span></span> <span data-ttu-id="3da6e-110">Тип этого значения будет вариант указанного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="3da6e-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3da6e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3da6e-111">Remarks</span></span>  
 <span data-ttu-id="3da6e-112">Ниже приведены идентификаторы GUID, которые поддерживаются для этого метода.</span><span class="sxs-lookup"><span data-stu-id="3da6e-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="3da6e-113">Описание, см. в разделе [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3da6e-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="3da6e-114">Если `optionId` находится не в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG`, указывающее, неверный параметр.</span><span class="sxs-lookup"><span data-stu-id="3da6e-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="3da6e-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="3da6e-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="3da6e-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="3da6e-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="3da6e-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="3da6e-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="3da6e-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="3da6e-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="3da6e-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="3da6e-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="3da6e-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="3da6e-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="3da6e-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="3da6e-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da6e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="3da6e-122">Requirements</span></span>  
 <span data-ttu-id="3da6e-123">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3da6e-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da6e-124">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3da6e-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3da6e-125">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3da6e-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3da6e-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da6e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da6e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3da6e-127">See also</span></span>

- [<span data-ttu-id="3da6e-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="3da6e-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3da6e-129">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="3da6e-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
