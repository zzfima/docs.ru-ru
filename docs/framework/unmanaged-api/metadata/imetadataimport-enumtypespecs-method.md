---
title: Метод IMetaDataImport::EnumTypeSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9b9bc8e364342a601c0738d5a64c5eac3cb7e7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447714"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="a5210-102">Метод IMetaDataImport::EnumTypeSpecs</span><span class="sxs-lookup"><span data-stu-id="a5210-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="a5210-103">Перечисляет токены TypeSpec, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a5210-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5210-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5210-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5210-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5210-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a5210-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a5210-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a5210-107">Это значение должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="a5210-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="a5210-108">[out] Массив, используемый для хранения токены TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="a5210-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a5210-109">[in] Максимальный размер массива `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="a5210-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="a5210-110">[out] Число токены TypeSpec, возвращаемых в `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="a5210-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5210-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5210-111">Return Value</span></span>  
  
|<span data-ttu-id="a5210-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5210-112">HRESULT</span></span>|<span data-ttu-id="a5210-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a5210-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a5210-114">`EnumTypeSpecs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a5210-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a5210-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="a5210-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a5210-116">В этом случае `pcTypeSpecs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a5210-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5210-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5210-117">Remarks</span></span>  
 <span data-ttu-id="a5210-118">Токены TypeSpec, создаются [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a5210-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5210-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a5210-119">Requirements</span></span>  
 <span data-ttu-id="a5210-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5210-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5210-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5210-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5210-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5210-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5210-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5210-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5210-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a5210-124">See Also</span></span>  
 [<span data-ttu-id="a5210-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a5210-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a5210-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a5210-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
