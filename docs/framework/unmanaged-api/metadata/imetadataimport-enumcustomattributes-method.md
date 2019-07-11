---
title: Метод IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c38b7f060c34f7408195484dec2c49305db422fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781325"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="680b3-102">Метод IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="680b3-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="680b3-103">Перечисляет токены определений настраиваемых атрибутов, связанных с указанным типом или членом.</span><span class="sxs-lookup"><span data-stu-id="680b3-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="680b3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="680b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="680b3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="680b3-106">[in, out] Указатель на возвращенном перечислителе.</span><span class="sxs-lookup"><span data-stu-id="680b3-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="680b3-107">[in] Маркер в рамках перечисление, или ноль для всех настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="680b3-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="680b3-108">[in] Маркер для конструктора типа атрибутов, которые необходимо перечислить или `null` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="680b3-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="680b3-109">[out] Массив настраиваемых атрибутов маркеров.</span><span class="sxs-lookup"><span data-stu-id="680b3-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="680b3-110">[in] Максимальный размер массива `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="680b3-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="680b3-111">[out, optional] Фактическое число маркеров значения, возвращаемые в `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="680b3-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="680b3-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="680b3-112">Return Value</span></span>  
  
|<span data-ttu-id="680b3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="680b3-113">HRESULT</span></span>|<span data-ttu-id="680b3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="680b3-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="680b3-115">`EnumCustomAttributes` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="680b3-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="680b3-116">Нет никаких настраиваемых атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="680b3-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="680b3-117">В этом случае `pcCustomAttributes` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="680b3-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="680b3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="680b3-118">Requirements</span></span>  
 <span data-ttu-id="680b3-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="680b3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="680b3-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="680b3-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="680b3-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="680b3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="680b3-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="680b3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680b3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="680b3-123">See also</span></span>

- [<span data-ttu-id="680b3-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="680b3-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="680b3-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="680b3-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
