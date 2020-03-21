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
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175529"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="9c7a6-102">Метод IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="9c7a6-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="9c7a6-103">Перечисляет пользовательские маркеры определения атрибутов, связанные с указанным типом или участником.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c7a6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9c7a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c7a6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9c7a6-106">(в, вне) Указатель на возвращенный регистратор.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="9c7a6-107">(в) Токен для области перечисления или ноль для всех пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="9c7a6-108">(в) Токен для конструктора типа атрибутов, которые будут перечислены, `null` или для всех типов.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="9c7a6-109">(ваут) Массив пользовательских токенов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9c7a6-110">[in] Максимальный размер массива `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="9c7a6-111">(вне, необязательно) Фактическое количество значений токенов, возвращенных в `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c7a6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c7a6-112">Return Value</span></span>  
  
|<span data-ttu-id="9c7a6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c7a6-113">HRESULT</span></span>|<span data-ttu-id="9c7a6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9c7a6-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9c7a6-115">`EnumCustomAttributes`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9c7a6-116">Нет пользовательских атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="9c7a6-117">В этом `pcCustomAttributes` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="9c7a6-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c7a6-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9c7a6-118">Requirements</span></span>  
 <span data-ttu-id="9c7a6-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c7a6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c7a6-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9c7a6-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c7a6-121">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c7a6-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c7a6-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7a6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7a6-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9c7a6-123">See also</span></span>

- [<span data-ttu-id="9c7a6-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9c7a6-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9c7a6-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9c7a6-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
