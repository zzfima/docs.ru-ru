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
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447467"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="27476-102">Метод IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="27476-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="27476-103">Перечисляет токены MethodDef, представляющие реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="27476-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27476-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27476-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27476-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27476-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="27476-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="27476-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="27476-107">[in] Токен TypeDef которого токены MethodDef, представляющие реализации интерфейса, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="27476-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="27476-108">[out] Массив, используемый для хранения токены MethodDef.</span><span class="sxs-lookup"><span data-stu-id="27476-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="27476-109">[in] Максимальный размер массива `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="27476-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="27476-110">[out] Фактическое число маркеров, возвращаемых в `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="27476-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27476-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27476-111">Return Value</span></span>  
  
|<span data-ttu-id="27476-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27476-112">HRESULT</span></span>|<span data-ttu-id="27476-113">Описание</span><span class="sxs-lookup"><span data-stu-id="27476-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="27476-114">`EnumInterfaceImpls` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="27476-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="27476-115">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="27476-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="27476-116">В этом случае `pcImpls` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="27476-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27476-117">Требования</span><span class="sxs-lookup"><span data-stu-id="27476-117">Requirements</span></span>  
 <span data-ttu-id="27476-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27476-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27476-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27476-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27476-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27476-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27476-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27476-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27476-122">См. также</span><span class="sxs-lookup"><span data-stu-id="27476-122">See Also</span></span>  
 [<span data-ttu-id="27476-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="27476-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="27476-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="27476-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
