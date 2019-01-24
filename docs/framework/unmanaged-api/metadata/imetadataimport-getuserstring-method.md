---
title: Метод IMetaDataImport::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e806bae1911ea6ffc5bb6e9af76d99524636d39e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491156"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="731ac-102">Метод IMetaDataImport::GetUserString</span><span class="sxs-lookup"><span data-stu-id="731ac-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="731ac-103">Получает строку литералов, представленную указанным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="731ac-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="731ac-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="731ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="731ac-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="731ac-106">[in] Токен строки, для возврата в связанной строке.</span><span class="sxs-lookup"><span data-stu-id="731ac-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="731ac-107">[out] Копия запрошенную строку.</span><span class="sxs-lookup"><span data-stu-id="731ac-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="731ac-108">[in] Максимальный размер в расширенных символах запрашиваемого `szString`.</span><span class="sxs-lookup"><span data-stu-id="731ac-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="731ac-109">[out] Размер в расширенных символах возвращаемого `szString`.</span><span class="sxs-lookup"><span data-stu-id="731ac-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="731ac-110">Требования</span><span class="sxs-lookup"><span data-stu-id="731ac-110">Requirements</span></span>  
 <span data-ttu-id="731ac-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="731ac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="731ac-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="731ac-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="731ac-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="731ac-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="731ac-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="731ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731ac-115">См. также</span><span class="sxs-lookup"><span data-stu-id="731ac-115">See also</span></span>
- [<span data-ttu-id="731ac-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="731ac-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="731ac-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="731ac-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
