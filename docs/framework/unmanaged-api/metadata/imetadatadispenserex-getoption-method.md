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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177721"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="80c2b-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="80c2b-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="80c2b-103">Получает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="80c2b-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="80c2b-104">Опция контролирует обработку вызовов в текущую область метаданных.</span><span class="sxs-lookup"><span data-stu-id="80c2b-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c2b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80c2b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c2b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="80c2b-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="80c2b-107">(в) Указатель на GUID, который определяет возможность для извлечения.</span><span class="sxs-lookup"><span data-stu-id="80c2b-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="80c2b-108">Ознакомьтесь с разделом «Замечания» для получения списка поддерживаемых GUID.</span><span class="sxs-lookup"><span data-stu-id="80c2b-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="80c2b-109">(ваут) Значение возвращенного опциона.</span><span class="sxs-lookup"><span data-stu-id="80c2b-109">[out] The value of the returned option.</span></span> <span data-ttu-id="80c2b-110">Тип этого значения будет вариантом указанного типа опции.</span><span class="sxs-lookup"><span data-stu-id="80c2b-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80c2b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="80c2b-111">Remarks</span></span>  
 <span data-ttu-id="80c2b-112">В следующем списке показаны GUID, которые поддерживаются для этого метода.</span><span class="sxs-lookup"><span data-stu-id="80c2b-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="80c2b-113">Для описания см. [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)</span><span class="sxs-lookup"><span data-stu-id="80c2b-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="80c2b-114">Если `optionId` его нет в этом списке, этот метод возвращает HRESULT, `E_INVALIDARG`указывая неправильный параметр.</span><span class="sxs-lookup"><span data-stu-id="80c2b-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="80c2b-115">MetaDataCheckМилидаксДля</span><span class="sxs-lookup"><span data-stu-id="80c2b-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="80c2b-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="80c2b-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="80c2b-117">MetaDataNotificationForTo</span><span class="sxs-lookup"><span data-stu-id="80c2b-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="80c2b-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="80c2b-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="80c2b-119">MetaDataErrorIfEmitOutOrder</span><span class="sxs-lookup"><span data-stu-id="80c2b-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="80c2b-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="80c2b-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="80c2b-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="80c2b-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c2b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="80c2b-122">Requirements</span></span>  
 <span data-ttu-id="80c2b-123">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80c2b-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c2b-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80c2b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80c2b-125">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80c2b-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80c2b-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c2b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c2b-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80c2b-127">See also</span></span>

- [<span data-ttu-id="80c2b-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="80c2b-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="80c2b-129">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="80c2b-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
