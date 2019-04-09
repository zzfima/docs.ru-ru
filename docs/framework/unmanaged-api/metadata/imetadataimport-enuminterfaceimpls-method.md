---
title: Метод IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136504"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="253a0-102">Метод IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="253a0-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="253a0-103">Перечисляет все интерфейсы, реализованные с помощью указанного `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="253a0-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="253a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="253a0-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="253a0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="253a0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="253a0-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="253a0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="253a0-107">[in] Токен TypeDef, которого токены MethodDef, представляющие реализации интерфейса, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="253a0-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="253a0-108">[out] Массив, используемый для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="253a0-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="253a0-109">[in] Максимальный размер массива `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="253a0-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="253a0-110">[out] Фактическое число маркеров, возвращаемых в `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="253a0-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="253a0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="253a0-111">Return Value</span></span>  
  
|<span data-ttu-id="253a0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="253a0-112">HRESULT</span></span>|<span data-ttu-id="253a0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="253a0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` <span data-ttu-id="253a0-114">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="253a0-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="253a0-115">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="253a0-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="253a0-116">В этом случае `pcImpls` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="253a0-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="253a0-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="253a0-117">Remarks</span></span>

<span data-ttu-id="253a0-118">Перечисление возвращает коллекцию `mdInterfaceImpl` маркеры для каждого интерфейса, реализуемый указанного `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="253a0-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="253a0-119">Интерфейс маркеры возвращаются в порядке, указанном интерфейсы были (через `DefineTypeDef` или `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="253a0-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="253a0-120">Свойствам возвращенного типа сущности `mdInterfaceImpl` маркеры можно запросить с помощью [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="253a0-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="253a0-121">Требования</span><span class="sxs-lookup"><span data-stu-id="253a0-121">Requirements</span></span>  
 <span data-ttu-id="253a0-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="253a0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="253a0-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="253a0-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="253a0-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="253a0-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="253a0-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="253a0-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="253a0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="253a0-126">See also</span></span>

- [<span data-ttu-id="253a0-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="253a0-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="253a0-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="253a0-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
