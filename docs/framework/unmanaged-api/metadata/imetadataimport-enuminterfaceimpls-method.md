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
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338063"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="e549b-102">Метод IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="e549b-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="e549b-103">Перечисляет все интерфейсы, реализованные указанным `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="e549b-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e549b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e549b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e549b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e549b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e549b-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="e549b-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="e549b-107">окне Токен TypeDef, маркеры MethodDef которого представляют реализации интерфейса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="e549b-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="e549b-108">заполняет Массив, используемый для хранения маркеров MethodDef.</span><span class="sxs-lookup"><span data-stu-id="e549b-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e549b-109">окне Максимальная длина массива `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="e549b-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="e549b-110">заполняет Фактическое число токенов, возвращаемых в `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="e549b-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e549b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e549b-111">Return Value</span></span>  
  
|<span data-ttu-id="e549b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e549b-112">HRESULT</span></span>|<span data-ttu-id="e549b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e549b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e549b-114">`EnumInterfaceImpls` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="e549b-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e549b-115">Отсутствуют токены MethodDef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="e549b-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="e549b-116">В этом случае `pcImpls` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="e549b-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="e549b-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="e549b-117">Remarks</span></span>

<span data-ttu-id="e549b-118">Перечисление Возвращает коллекцию токенов `mdInterfaceImpl` для каждого интерфейса, реализованного с помощью указанного `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="e549b-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="e549b-119">Маркеры интерфейса возвращаются в том порядке, в котором были указаны интерфейсы (с помощью `DefineTypeDef` или `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="e549b-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="e549b-120">Свойства возвращенных маркеров `mdInterfaceImpl` можно запрашивать с помощью [жетинтерфацеимплпропс](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="e549b-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="e549b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e549b-121">Requirements</span></span>  
 <span data-ttu-id="e549b-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e549b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e549b-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e549b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e549b-124">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e549b-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e549b-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e549b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e549b-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e549b-126">See also</span></span>

- [<span data-ttu-id="e549b-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e549b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e549b-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e549b-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
