---
title: Метод IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de8547ed0ee83bafe4612bdcd62607fc94fb3f69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043801"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="fdcbe-102">Метод IMetaDataEmit2::DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="fdcbe-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="fdcbe-103">Создает определение для параметра универсального типа и возвращает маркер для этого параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdcbe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdcbe-104">Syntax</span></span>  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdcbe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fdcbe-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fdcbe-106">[in] `mdTypeDef` Или `mdMethodDef` токен, представляющий метод или конструктор, для которого необходимо определить универсальный параметр.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="fdcbe-107">[in] Индекс универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="fdcbe-108">[in] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее тип универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="fdcbe-109">[in] Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="fdcbe-110">[in] Этот параметр зарезервирован для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="fdcbe-111">[in] Массив типа ограничения, оканчивающаяся нулем.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="fdcbe-112">Элементы массива должны быть `mdTypeDef`, `mdTypeRef`, или `mdTypeSpec` токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="fdcbe-113">[out] Токен, который представляет универсальный параметр.</span><span class="sxs-lookup"><span data-stu-id="fdcbe-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdcbe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fdcbe-114">Requirements</span></span>  
 <span data-ttu-id="fdcbe-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdcbe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdcbe-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fdcbe-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fdcbe-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdcbe-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fdcbe-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdcbe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdcbe-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fdcbe-119">See also</span></span>

- [<span data-ttu-id="fdcbe-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fdcbe-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="fdcbe-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fdcbe-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
