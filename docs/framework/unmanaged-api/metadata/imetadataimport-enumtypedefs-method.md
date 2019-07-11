---
title: Метод IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 621582536c07b269dd723c9014e23c50e561957a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774612"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="57b49-102">Метод IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="57b49-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="57b49-103">Перечисляет токены TypeDef, представляющие все типы в текущей области.</span><span class="sxs-lookup"><span data-stu-id="57b49-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57b49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57b49-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57b49-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57b49-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="57b49-106">[out] Указатель на новый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="57b49-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="57b49-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="57b49-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="57b49-108">[in] Массив, используемый для хранения токенов TypeDef.</span><span class="sxs-lookup"><span data-stu-id="57b49-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="57b49-109">[in] Максимальный размер массива `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="57b49-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="57b49-110">[out] Число маркеров TypeDef, возвращаемых в `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="57b49-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57b49-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57b49-111">Return Value</span></span>  
  
|<span data-ttu-id="57b49-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57b49-112">HRESULT</span></span>|<span data-ttu-id="57b49-113">Описание</span><span class="sxs-lookup"><span data-stu-id="57b49-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="57b49-114">`EnumTypeDefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="57b49-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="57b49-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="57b49-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="57b49-116">В этом случае `pcTypeDefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="57b49-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57b49-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="57b49-117">Remarks</span></span>  
 <span data-ttu-id="57b49-118">Токен TypeDef представляет тип, например класс или интерфейс, а также любой тип, добавлены через механизм расширяемости.</span><span class="sxs-lookup"><span data-stu-id="57b49-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57b49-119">Требования</span><span class="sxs-lookup"><span data-stu-id="57b49-119">Requirements</span></span>  
 <span data-ttu-id="57b49-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57b49-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57b49-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="57b49-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57b49-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57b49-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57b49-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b49-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b49-124">См. также</span><span class="sxs-lookup"><span data-stu-id="57b49-124">See also</span></span>

- [<span data-ttu-id="57b49-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="57b49-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="57b49-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="57b49-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
