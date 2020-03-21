---
title: Метод IMetaDataImport::EnumMethodImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175477"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="9ca61-102">Метод IMetaDataImport::EnumMethodImpls</span><span class="sxs-lookup"><span data-stu-id="9ca61-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="9ca61-103">Перечисляет токены MethodBody и MethodDeclaration, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="9ca61-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ca61-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ca61-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ca61-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9ca61-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="9ca61-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9ca61-107">Это должно быть NULL для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="9ca61-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="9ca61-108">(в) Токен TypeDef для типа, метод реализации которого перечислять.</span><span class="sxs-lookup"><span data-stu-id="9ca61-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="9ca61-109">(ваут) Массив для хранения токенов MethodBody.</span><span class="sxs-lookup"><span data-stu-id="9ca61-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="9ca61-110">(ваут) Массив для хранения токенов MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="9ca61-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9ca61-111">(в) Максимальный размер `rMethodBody` и `rMethodDecl` массивов.</span><span class="sxs-lookup"><span data-stu-id="9ca61-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="9ca61-112">(в) Фактическое количество методов, `rMethodBody` `rMethodDecl`возвращенных в и .</span><span class="sxs-lookup"><span data-stu-id="9ca61-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ca61-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9ca61-113">Return Value</span></span>  
  
|<span data-ttu-id="9ca61-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ca61-114">HRESULT</span></span>|<span data-ttu-id="9ca61-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9ca61-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9ca61-116">`EnumMethodImpls`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="9ca61-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9ca61-117">Нет маркеров метода для перечисления.</span><span class="sxs-lookup"><span data-stu-id="9ca61-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="9ca61-118">В этом `pcTokens` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="9ca61-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ca61-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9ca61-119">Requirements</span></span>  
 <span data-ttu-id="9ca61-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ca61-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca61-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ca61-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ca61-122">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ca61-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9ca61-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca61-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca61-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ca61-124">See also</span></span>

- [<span data-ttu-id="9ca61-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9ca61-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9ca61-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9ca61-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
