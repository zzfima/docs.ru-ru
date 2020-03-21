---
title: Метод IMetaDataEmit::DefineUserString
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: a71d8694ec8c5bd35ecd3e98ed32e05bc7b382fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177616"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="c618d-102">Метод IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="c618d-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="c618d-103">Получает токен метаданных для указанной буквальной строки.</span><span class="sxs-lookup"><span data-stu-id="c618d-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c618d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c618d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c618d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c618d-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="c618d-106">(в) Строка пользователя для хранения.</span><span class="sxs-lookup"><span data-stu-id="c618d-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="c618d-107">(в) Количество широких символов `szString`в .</span><span class="sxs-lookup"><span data-stu-id="c618d-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="c618d-108">(ваут) Назначен маркер строки.</span><span class="sxs-lookup"><span data-stu-id="c618d-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c618d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c618d-109">Requirements</span></span>  
 <span data-ttu-id="c618d-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c618d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c618d-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c618d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c618d-112">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c618d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c618d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c618d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c618d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c618d-114">See also</span></span>

- [<span data-ttu-id="c618d-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c618d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c618d-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c618d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
