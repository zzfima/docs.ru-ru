---
title: Метод IMetaDataTables::GetCodedTokenInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a9eb51643271fd27a6d4795fc1729766b44b239
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468797"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="0368b-102">Метод IMetaDataTables::GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="0368b-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="0368b-103">Получает указатель на массив токенов, связанных с заданного индекса строки.</span><span class="sxs-lookup"><span data-stu-id="0368b-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0368b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0368b-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0368b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0368b-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="0368b-106">[in] Вид закодированный токен для возврата.</span><span class="sxs-lookup"><span data-stu-id="0368b-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0368b-107">[out] Указатель на длину `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="0368b-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="0368b-108">[out] Указатель на указатель на массив, содержащий список возвращаемые метки.</span><span class="sxs-lookup"><span data-stu-id="0368b-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="0368b-109">[out] Указатель на указатель на имя маркера в `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="0368b-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0368b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0368b-110">Requirements</span></span>  
 <span data-ttu-id="0368b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0368b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0368b-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0368b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0368b-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0368b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0368b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0368b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0368b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0368b-115">See also</span></span>
- [<span data-ttu-id="0368b-116">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="0368b-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0368b-117">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="0368b-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
