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
ms.openlocfilehash: 193e8788d5a1b28f43f2fb0d4d935a18542dd923
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427492"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="0fce3-102">Метод IMetaDataImport::EnumMethodImpls</span><span class="sxs-lookup"><span data-stu-id="0fce3-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="0fce3-103">Перечисляет токены MethodBody и MethodDeclaration, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="0fce3-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fce3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fce3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0fce3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fce3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0fce3-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="0fce3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0fce3-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="0fce3-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="0fce3-108">окне Токен TypeDef для типа, реализации методов которого требуется перечислить.</span><span class="sxs-lookup"><span data-stu-id="0fce3-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="0fce3-109">заполняет Массив для хранения токенов Месодбоди.</span><span class="sxs-lookup"><span data-stu-id="0fce3-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="0fce3-110">заполняет Массив для хранения токенов MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="0fce3-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0fce3-111">окне Максимальный размер массивов `rMethodBody` и `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="0fce3-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0fce3-112">окне Фактическое число методов, возвращаемых в `rMethodBody` и `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="0fce3-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fce3-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0fce3-113">Return Value</span></span>  
  
|<span data-ttu-id="0fce3-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0fce3-114">HRESULT</span></span>|<span data-ttu-id="0fce3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0fce3-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0fce3-116">`EnumMethodImpls` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0fce3-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0fce3-117">Нет токенов метода для перечисления.</span><span class="sxs-lookup"><span data-stu-id="0fce3-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="0fce3-118">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="0fce3-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fce3-119">Требования</span><span class="sxs-lookup"><span data-stu-id="0fce3-119">Requirements</span></span>  
 <span data-ttu-id="0fce3-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fce3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fce3-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="0fce3-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fce3-122">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0fce3-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fce3-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fce3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fce3-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0fce3-124">See also</span></span>

- [<span data-ttu-id="0fce3-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0fce3-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0fce3-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0fce3-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
