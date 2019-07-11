---
title: Метод IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8cd086a86d104fdfebf1a8298a22b795cb2389b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782649"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="8f53b-102">Метод IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="8f53b-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="8f53b-103">Получает перечислитель для массива MethodSpec токенов, связанных с указанным MethodDef или MemberRef маркер.</span><span class="sxs-lookup"><span data-stu-id="8f53b-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f53b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f53b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8f53b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f53b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8f53b-106">[in, out] Указатель на перечислитель для `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="8f53b-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="8f53b-107">[in] Токен MemberRef или MethodDef, представляющий метод, маркеры которого MethodSpec будут перечислены.</span><span class="sxs-lookup"><span data-stu-id="8f53b-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="8f53b-108">Если значение `tk` равно 0 (ноль), будут перечислены все маркеры MethodSpec в области.</span><span class="sxs-lookup"><span data-stu-id="8f53b-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="8f53b-109">[out] Массив MethodSpec маркеры для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8f53b-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8f53b-110">[in] Максимальное число маркеров для размещения в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="8f53b-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="8f53b-111">[out] Возвращенное число маркеров помещаются в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="8f53b-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f53b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f53b-112">Return Value</span></span>  
  
|<span data-ttu-id="8f53b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f53b-113">HRESULT</span></span>|<span data-ttu-id="8f53b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8f53b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8f53b-115">`EnumMethodSpecs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8f53b-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8f53b-116">`phEnum` не имеет члена элементов.</span><span class="sxs-lookup"><span data-stu-id="8f53b-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="8f53b-117">В этом случае `pcMethodSpecs` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="8f53b-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f53b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8f53b-118">Requirements</span></span>  
 <span data-ttu-id="8f53b-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f53b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f53b-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f53b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f53b-121">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f53b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f53b-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f53b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f53b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8f53b-123">See also</span></span>

- [<span data-ttu-id="8f53b-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8f53b-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="8f53b-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8f53b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
