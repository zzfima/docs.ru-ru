---
title: "Метод IMetaDataTables::GetCodedTokenInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetCodedTokenInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eb9b732ab26c8d0caa466cb8e6816968eb0646d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="91236-102">Метод IMetaDataTables::GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="91236-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="91236-103">Возвращает указатель на массив маркеров, связанных с заданным индексом строки.</span><span class="sxs-lookup"><span data-stu-id="91236-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91236-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91236-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91236-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="91236-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="91236-106">[in] Вид закодированного маркер для возвращения.</span><span class="sxs-lookup"><span data-stu-id="91236-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="91236-107">[out] Указатель на длину `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="91236-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="91236-108">[out] Указатель на указатель на массив, содержащий список возвращенных токенов.</span><span class="sxs-lookup"><span data-stu-id="91236-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="91236-109">[out] Указатель на указатель на имя маркер на `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="91236-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91236-110">Требования</span><span class="sxs-lookup"><span data-stu-id="91236-110">Requirements</span></span>  
 <span data-ttu-id="91236-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91236-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91236-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="91236-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91236-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91236-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91236-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91236-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91236-115">См. также</span><span class="sxs-lookup"><span data-stu-id="91236-115">See Also</span></span>  
 [<span data-ttu-id="91236-116">IMetaDataTables-интерфейс</span><span class="sxs-lookup"><span data-stu-id="91236-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="91236-117">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="91236-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
