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
ms.openlocfilehash: 358346af540c8b6b7ee1523e763bebbacf8cd2bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127820"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="0ac37-102">Метод IMetaDataImport::GetUserString</span><span class="sxs-lookup"><span data-stu-id="0ac37-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="0ac37-103">Получает строку литералов, представленную указанным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="0ac37-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ac37-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ac37-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ac37-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="0ac37-106">[in] Токен строки, для возврата в связанной строке.</span><span class="sxs-lookup"><span data-stu-id="0ac37-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="0ac37-107">[out] Копия запрошенную строку.</span><span class="sxs-lookup"><span data-stu-id="0ac37-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="0ac37-108">[in] Максимальный размер в расширенных символах запрашиваемого `szString`.</span><span class="sxs-lookup"><span data-stu-id="0ac37-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="0ac37-109">[out] Размер в расширенных символах возвращаемого `szString`.</span><span class="sxs-lookup"><span data-stu-id="0ac37-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac37-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0ac37-110">Requirements</span></span>  
 <span data-ttu-id="0ac37-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ac37-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ac37-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ac37-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ac37-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ac37-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ac37-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ac37-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac37-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0ac37-115">See also</span></span>

- [<span data-ttu-id="0ac37-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0ac37-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0ac37-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0ac37-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
