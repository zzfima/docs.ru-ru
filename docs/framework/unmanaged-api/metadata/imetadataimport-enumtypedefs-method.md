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
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177295"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="41299-102">Метод IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="41299-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="41299-103">Перечисляет токены TypeDef, представляющие все типы в текущей области.</span><span class="sxs-lookup"><span data-stu-id="41299-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41299-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41299-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41299-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41299-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="41299-106">(ваут) Указатель на новый регистратор.</span><span class="sxs-lookup"><span data-stu-id="41299-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="41299-107">Это должно быть NULL для первого вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="41299-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="41299-108">(в) Массив, используемый для хранения токенов TypeDef.</span><span class="sxs-lookup"><span data-stu-id="41299-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="41299-109">[in] Максимальный размер массива `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="41299-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="41299-110">(ваут) Число возвращенных токенов TypeDef `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="41299-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41299-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="41299-111">Return Value</span></span>  
  
|<span data-ttu-id="41299-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41299-112">HRESULT</span></span>|<span data-ttu-id="41299-113">Описание</span><span class="sxs-lookup"><span data-stu-id="41299-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="41299-114">`EnumTypeDefs`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="41299-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="41299-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="41299-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="41299-116">В этом `pcTypeDefs` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="41299-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41299-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="41299-117">Remarks</span></span>  
 <span data-ttu-id="41299-118">Токен TypeDef представляет собой тип, например класс или интерфейс, а также любой тип, добавленный с помощью механизма расширяемости.</span><span class="sxs-lookup"><span data-stu-id="41299-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41299-119">Требования</span><span class="sxs-lookup"><span data-stu-id="41299-119">Requirements</span></span>  
 <span data-ttu-id="41299-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41299-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41299-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41299-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41299-122">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41299-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41299-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41299-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41299-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="41299-124">See also</span></span>

- [<span data-ttu-id="41299-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="41299-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="41299-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="41299-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
