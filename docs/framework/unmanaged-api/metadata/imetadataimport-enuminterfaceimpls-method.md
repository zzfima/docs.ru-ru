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
ms.openlocfilehash: 0d0f94949cdc82cdecd52f003f3400c43014fabf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780466"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="6dab4-102">Метод IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="6dab4-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="6dab4-103">Перечисляет все интерфейсы, реализованные с помощью указанного `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="6dab4-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="6dab4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6dab4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dab4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6dab4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6dab4-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="6dab4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="6dab4-107">[in] Токен TypeDef, которого токены MethodDef, представляющие реализации интерфейса, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="6dab4-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="6dab4-108">[out] Массив, используемый для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="6dab4-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6dab4-109">[in] Максимальный размер массива `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="6dab4-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="6dab4-110">[out] Фактическое число маркеров, возвращаемых в `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="6dab4-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dab4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6dab4-111">Return Value</span></span>  
  
|<span data-ttu-id="6dab4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6dab4-112">HRESULT</span></span>|<span data-ttu-id="6dab4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6dab4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6dab4-114">`EnumInterfaceImpls` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6dab4-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6dab4-115">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="6dab4-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="6dab4-116">В этом случае `pcImpls` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="6dab4-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="6dab4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="6dab4-117">Remarks</span></span>

<span data-ttu-id="6dab4-118">Перечисление возвращает коллекцию `mdInterfaceImpl` маркеры для каждого интерфейса, реализуемый указанного `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="6dab4-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="6dab4-119">Интерфейс маркеры возвращаются в порядке, указанном интерфейсы были (через `DefineTypeDef` или `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="6dab4-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="6dab4-120">Свойствам возвращенного типа сущности `mdInterfaceImpl` маркеры можно запросить с помощью [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="6dab4-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6dab4-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6dab4-121">Requirements</span></span>  
 <span data-ttu-id="6dab4-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dab4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dab4-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6dab4-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6dab4-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dab4-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6dab4-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dab4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dab4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6dab4-126">See also</span></span>

- [<span data-ttu-id="6dab4-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6dab4-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6dab4-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6dab4-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
