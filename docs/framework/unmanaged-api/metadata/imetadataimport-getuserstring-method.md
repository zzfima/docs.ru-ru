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
ms.openlocfilehash: 474338ff1780ce9b442208cd06f8b14bc411be5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447753"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="aaadb-102">Метод IMetaDataImport::GetUserString</span><span class="sxs-lookup"><span data-stu-id="aaadb-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="aaadb-103">Получает строку литералов, представленную указанным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="aaadb-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaadb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaadb-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaadb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aaadb-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="aaadb-106">[in] Маркер строки для возвращения в связанной строке.</span><span class="sxs-lookup"><span data-stu-id="aaadb-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="aaadb-107">[out] Копия Запрошенная строка.</span><span class="sxs-lookup"><span data-stu-id="aaadb-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="aaadb-108">[in] Максимальный размер в расширенные символы запрашиваемого `szString`.</span><span class="sxs-lookup"><span data-stu-id="aaadb-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="aaadb-109">[out] Размер в расширенные символы возвращаемого `szString`.</span><span class="sxs-lookup"><span data-stu-id="aaadb-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaadb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="aaadb-110">Requirements</span></span>  
 <span data-ttu-id="aaadb-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaadb-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aaadb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aaadb-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aaadb-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aaadb-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaadb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaadb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="aaadb-115">See Also</span></span>  
 [<span data-ttu-id="aaadb-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="aaadb-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="aaadb-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="aaadb-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
