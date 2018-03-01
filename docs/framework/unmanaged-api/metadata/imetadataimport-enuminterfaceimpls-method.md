---
title: "Метод IMetaDataImport::EnumInterfaceImpls"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 646d65ff81795ce0558651db9c3fe1bc7205ae08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="2c4b9-102">Метод IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="2c4b9-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="2c4b9-103">Перечисляет токены MethodDef, представляющие реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c4b9-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c4b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2c4b9-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="2c4b9-107">[in] Токен TypeDef которого токены MethodDef, представляющие реализации интерфейса, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="2c4b9-108">[out] Массив, используемый для хранения токены MethodDef.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2c4b9-109">[in] Максимальный размер массива `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="2c4b9-110">[out] Фактическое число маркеров, возвращаемых в `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c4b9-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4b9-111">Return Value</span></span>  
  
|<span data-ttu-id="2c4b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c4b9-112">HRESULT</span></span>|<span data-ttu-id="2c4b9-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="2c4b9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2c4b9-114">`EnumInterfaceImpls`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2c4b9-115">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="2c4b9-116">В этом случае `pcImpls` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="2c4b9-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c4b9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2c4b9-117">Requirements</span></span>  
 <span data-ttu-id="2c4b9-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c4b9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c4b9-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c4b9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c4b9-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c4b9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c4b9-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c4b9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4b9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2c4b9-122">See Also</span></span>  
 [<span data-ttu-id="2c4b9-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2c4b9-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2c4b9-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2c4b9-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
