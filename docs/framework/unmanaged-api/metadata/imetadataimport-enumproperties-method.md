---
title: Метод IMetaDataImport::EnumProperties
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
ms.openlocfilehash: 4fed7dbe4ec8343a3854d1f277e3228b14c0bf21
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450027"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="2364b-102">Метод IMetaDataImport::EnumProperties</span><span class="sxs-lookup"><span data-stu-id="2364b-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="2364b-103">Перечисляет токены PropertyDef, представляющие свойства типа, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="2364b-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2364b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2364b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2364b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2364b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2364b-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="2364b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2364b-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="2364b-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="2364b-108">окне Токен TypeDef, представляющий тип со свойствами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="2364b-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="2364b-109">заполняет Массив, используемый для хранения маркеров Пропертидеф.</span><span class="sxs-lookup"><span data-stu-id="2364b-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2364b-110">[in] Максимальный размер массива `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="2364b-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="2364b-111">заполняет Число маркеров Пропертидеф, возвращаемых в `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="2364b-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2364b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2364b-112">Return Value</span></span>  
  
|<span data-ttu-id="2364b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2364b-113">HRESULT</span></span>|<span data-ttu-id="2364b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2364b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2364b-115">`EnumProperties` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2364b-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2364b-116">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="2364b-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="2364b-117">В этом случае `pcProperties` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="2364b-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2364b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="2364b-118">Requirements</span></span>  
 <span data-ttu-id="2364b-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2364b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2364b-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2364b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2364b-121">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2364b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2364b-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2364b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2364b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2364b-123">See also</span></span>

- [<span data-ttu-id="2364b-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2364b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2364b-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2364b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
