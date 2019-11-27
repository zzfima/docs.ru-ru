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
ms.openlocfilehash: edf24de8ae38aab97e41a53cc86ae5aa6c592c50
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434690"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="dfaae-102">Метод IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="dfaae-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="dfaae-103">Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.</span><span class="sxs-lookup"><span data-stu-id="dfaae-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfaae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfaae-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfaae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfaae-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="dfaae-106">окне Токен, для которого проверяется допустимость ссылки.</span><span class="sxs-lookup"><span data-stu-id="dfaae-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfaae-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dfaae-107">Return Value</span></span>  
 <span data-ttu-id="dfaae-108">`true`, если `tk` является допустимым маркером метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="dfaae-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="dfaae-109">В противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="dfaae-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfaae-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dfaae-110">Requirements</span></span>  
 <span data-ttu-id="dfaae-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfaae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfaae-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="dfaae-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dfaae-113">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dfaae-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dfaae-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfaae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfaae-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dfaae-115">See also</span></span>

- [<span data-ttu-id="dfaae-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="dfaae-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dfaae-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="dfaae-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
