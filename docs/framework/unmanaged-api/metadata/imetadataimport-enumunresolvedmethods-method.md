---
title: "Метод IMetaDataImport::EnumUnresolvedMethods"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUnresolvedMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4e77453fc11b77b602d4a89f0d90540c06b0a08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="02b72-102">Метод IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="02b72-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="02b72-103">Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="02b72-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02b72-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02b72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02b72-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="02b72-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="02b72-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="02b72-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="02b72-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="02b72-108">[out] Массив, используемый для хранения MemberDef токенов.</span><span class="sxs-lookup"><span data-stu-id="02b72-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="02b72-109">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="02b72-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="02b72-110">[out] Количество возвращаемых в токены MemberDef `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="02b72-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02b72-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="02b72-111">Return Value</span></span>  
  
|<span data-ttu-id="02b72-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02b72-112">HRESULT</span></span>|<span data-ttu-id="02b72-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="02b72-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="02b72-114">`EnumUnresolvedMethods`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="02b72-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="02b72-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="02b72-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="02b72-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="02b72-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02b72-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="02b72-117">Remarks</span></span>  
 <span data-ttu-id="02b72-118">Неразрешенный метод является один, который объявлен, но не реализован.</span><span class="sxs-lookup"><span data-stu-id="02b72-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="02b72-119">Метод включается в перечислении, если метод помечен `miForwardRef` и либо `mdPinvokeImpl` или `miRuntime` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="02b72-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="02b72-120">Другими словами, неразрешенный метод является методом класса, помеченного `miForwardRef` , но которой не реализован в неуправляемом коде (посредством PInvoke) не реализуются внутренне самой средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="02b72-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="02b72-121">Перечисление исключает все методы, определенные в области модуля (глобальные) или в интерфейсы или абстрактные классы.</span><span class="sxs-lookup"><span data-stu-id="02b72-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02b72-122">Требования</span><span class="sxs-lookup"><span data-stu-id="02b72-122">Requirements</span></span>  
 <span data-ttu-id="02b72-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02b72-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02b72-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="02b72-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02b72-125">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02b72-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02b72-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02b72-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b72-127">См. также</span><span class="sxs-lookup"><span data-stu-id="02b72-127">See Also</span></span>  
 [<span data-ttu-id="02b72-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="02b72-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="02b72-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="02b72-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
