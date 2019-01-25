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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb08bad82400523d82e4b8589acb2e74fbbd17d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603736"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="5a1bc-102">Метод IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="5a1bc-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="5a1bc-103">Получает маркер метаданных для заданной строки литерала.</span><span class="sxs-lookup"><span data-stu-id="5a1bc-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a1bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a1bc-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a1bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a1bc-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="5a1bc-106">[in] Строка пользователя для хранения.</span><span class="sxs-lookup"><span data-stu-id="5a1bc-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="5a1bc-107">[in] Число расширенных символов в `szString`.</span><span class="sxs-lookup"><span data-stu-id="5a1bc-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="5a1bc-108">[out] Маркер строки, назначенный.</span><span class="sxs-lookup"><span data-stu-id="5a1bc-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a1bc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5a1bc-109">Requirements</span></span>  
 <span data-ttu-id="5a1bc-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a1bc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a1bc-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a1bc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a1bc-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a1bc-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a1bc-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a1bc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1bc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5a1bc-114">See also</span></span>
- [<span data-ttu-id="5a1bc-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5a1bc-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5a1bc-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5a1bc-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
