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
ms.openlocfilehash: 6c2122c06c6e4f1137173f02e37fb0982864e7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448379"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="8bf7b-102">Метод IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="8bf7b-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="8bf7b-103">Возвращает перечислитель для массива маркеров MethodSpec, связанных с указанным MethodDef или MemberRef токен.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bf7b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bf7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bf7b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8bf7b-106">[in, out] Указатель на перечислитель для `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="8bf7b-107">[in] Токен MemberRef или MethodDef, представляющий метод, маркеры которого MethodSpec для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="8bf7b-108">Если значение `tk` равно 0 (ноль), будут перечислены все маркеры MethodSpec в области.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="8bf7b-109">[out] Массив MethodSpec маркеры для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8bf7b-110">[in] Максимальное количество маркеров для размещения в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="8bf7b-111">[out] Возвращенное число маркеров помещаются в `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bf7b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8bf7b-112">Return Value</span></span>  
  
|<span data-ttu-id="8bf7b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bf7b-113">HRESULT</span></span>|<span data-ttu-id="8bf7b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8bf7b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8bf7b-115">`EnumMethodSpecs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8bf7b-116">`phEnum` не имеет члена элементов.</span><span class="sxs-lookup"><span data-stu-id="8bf7b-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="8bf7b-117">В этом случае `pcMethodSpecs` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="8bf7b-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bf7b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8bf7b-118">Requirements</span></span>  
 <span data-ttu-id="8bf7b-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bf7b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf7b-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bf7b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bf7b-121">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bf7b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bf7b-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf7b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf7b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8bf7b-123">See Also</span></span>  
 [<span data-ttu-id="8bf7b-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8bf7b-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="8bf7b-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8bf7b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
