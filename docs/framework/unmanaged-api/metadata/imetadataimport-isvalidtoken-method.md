---
title: Метод IMetaDataImport::IsValidToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a99ed42f500b83b5109631b21a88029995b43d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123885"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="9a841-102">Метод IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="9a841-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="9a841-103">Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.</span><span class="sxs-lookup"><span data-stu-id="9a841-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a841-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a841-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a841-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a841-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9a841-106">[in] Токен для проверки допустимости для ссылки.</span><span class="sxs-lookup"><span data-stu-id="9a841-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a841-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a841-107">Return Value</span></span>  
 `true` <span data-ttu-id="9a841-108">Если `tk` является допустимым маркером метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="9a841-108">if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="9a841-109">В противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9a841-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a841-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9a841-110">Requirements</span></span>  
 <span data-ttu-id="9a841-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a841-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a841-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a841-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a841-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a841-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9a841-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9a841-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a841-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9a841-115">See also</span></span>

- [<span data-ttu-id="9a841-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9a841-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9a841-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9a841-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
