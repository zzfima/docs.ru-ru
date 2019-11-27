---
title: Метод IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449952"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="bf946-102">Метод IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="bf946-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="bf946-103">Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="bf946-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf946-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf946-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf946-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf946-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bf946-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="bf946-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bf946-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="bf946-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="bf946-108">заполняет Массив, используемый для хранения маркеров Мембердеф.</span><span class="sxs-lookup"><span data-stu-id="bf946-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bf946-109">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="bf946-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bf946-110">заполняет Число маркеров Мембердеф, возвращаемых в `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="bf946-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf946-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf946-111">Return Value</span></span>  
  
|<span data-ttu-id="bf946-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf946-112">HRESULT</span></span>|<span data-ttu-id="bf946-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bf946-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bf946-114">`EnumUnresolvedMethods` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="bf946-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bf946-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="bf946-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="bf946-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="bf946-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf946-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="bf946-117">Remarks</span></span>  
 <span data-ttu-id="bf946-118">Неразрешенный метод — это тот, который был объявлен, но не реализован.</span><span class="sxs-lookup"><span data-stu-id="bf946-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="bf946-119">Метод включается в перечисление, если метод помечается как `miForwardRef` и `mdPinvokeImpl` или `miRuntime` имеет нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="bf946-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="bf946-120">Иными словами, неразрешенный метод — это метод класса, который помечается как `miForwardRef`, но не реализован в неуправляемом коде (достигается через PInvoke) и не реализуется внутри самой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="bf946-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="bf946-121">Перечисление исключает все методы, определенные либо в области видимости модуля (Globals), либо в интерфейсах или в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="bf946-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf946-122">Требования</span><span class="sxs-lookup"><span data-stu-id="bf946-122">Requirements</span></span>  
 <span data-ttu-id="bf946-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf946-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf946-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bf946-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf946-125">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf946-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf946-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf946-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf946-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bf946-127">See also</span></span>

- [<span data-ttu-id="bf946-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bf946-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bf946-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bf946-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
