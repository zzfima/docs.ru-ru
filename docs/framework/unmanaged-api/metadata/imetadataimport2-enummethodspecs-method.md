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
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177176"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="90b30-102">Метод IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="90b30-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="90b30-103">Получает регистратор для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.</span><span class="sxs-lookup"><span data-stu-id="90b30-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90b30-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="90b30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90b30-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="90b30-106">(в, вне) Указатель на регистратор для `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="90b30-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="90b30-107">(в) Токен MemberRef или MethodDef, представляющий метод, токены которого должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="90b30-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="90b30-108">Если значение `tk` 0 (ноль), все токены MethodSpec в области будут перечислены.</span><span class="sxs-lookup"><span data-stu-id="90b30-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="90b30-109">(ваут) Массив токенов MethodSpec для перечисления.</span><span class="sxs-lookup"><span data-stu-id="90b30-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="90b30-110">(в) Запрошенное максимальное количество токенов `rMethodSpecs`для размещения в .</span><span class="sxs-lookup"><span data-stu-id="90b30-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="90b30-111">(ваут) Возвратное количество токенов, помещенных в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="90b30-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90b30-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="90b30-112">Return Value</span></span>  
  
|<span data-ttu-id="90b30-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90b30-113">HRESULT</span></span>|<span data-ttu-id="90b30-114">Описание</span><span class="sxs-lookup"><span data-stu-id="90b30-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="90b30-115">`EnumMethodSpecs`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="90b30-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="90b30-116">`phEnum`не имеет элементов-членов.</span><span class="sxs-lookup"><span data-stu-id="90b30-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="90b30-117">В этом `pcMethodSpecs` случае устанавливается до 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="90b30-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90b30-118">Требования</span><span class="sxs-lookup"><span data-stu-id="90b30-118">Requirements</span></span>  
 <span data-ttu-id="90b30-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90b30-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90b30-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90b30-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90b30-121">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90b30-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90b30-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90b30-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b30-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90b30-123">See also</span></span>

- [<span data-ttu-id="90b30-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="90b30-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="90b30-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="90b30-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
