---
title: Метод IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177309"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="459fc-102">Метод IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="459fc-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="459fc-103">Перечисляет токены MethodDef, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="459fc-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="459fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="459fc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="459fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="459fc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="459fc-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="459fc-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="459fc-107">Это должно быть NULL для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="459fc-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="459fc-108">(в) Токен TypeDef, представляющий тип с методами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="459fc-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="459fc-109">(ваут) Массив для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="459fc-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="459fc-110">(в) Максимальный размер массива `rMethods` MethodDef.</span><span class="sxs-lookup"><span data-stu-id="459fc-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="459fc-111">(ваут) Количество возвращенных токенов MethodDef `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="459fc-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="459fc-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="459fc-112">Return Value</span></span>  
  
|<span data-ttu-id="459fc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="459fc-113">HRESULT</span></span>|<span data-ttu-id="459fc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="459fc-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="459fc-115">`EnumMethods`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="459fc-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="459fc-116">Нет токенов MethodDef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="459fc-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="459fc-117">В этом `pcTokens` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="459fc-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="459fc-118">Требования</span><span class="sxs-lookup"><span data-stu-id="459fc-118">Requirements</span></span>  
 <span data-ttu-id="459fc-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="459fc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="459fc-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="459fc-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="459fc-121">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="459fc-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="459fc-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="459fc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459fc-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="459fc-123">See also</span></span>

- [<span data-ttu-id="459fc-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="459fc-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="459fc-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="459fc-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
