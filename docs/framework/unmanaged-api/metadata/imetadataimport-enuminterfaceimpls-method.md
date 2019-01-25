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
ms.openlocfilehash: c94960478e6b2eb4e7b8f1e9592b0831af3ec686
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603772"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="23c77-102">Метод IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="23c77-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="23c77-103">Перечисляет токены MethodDef, представляющие реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="23c77-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23c77-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23c77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="23c77-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="23c77-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="23c77-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="23c77-107">[in] Токен TypeDef, которого токены MethodDef, представляющие реализации интерфейса, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="23c77-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="23c77-108">[out] Массив, используемый для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="23c77-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="23c77-109">[in] Максимальный размер массива `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="23c77-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="23c77-110">[out] Фактическое число маркеров, возвращаемых в `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="23c77-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23c77-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="23c77-111">Return Value</span></span>  
  
|<span data-ttu-id="23c77-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23c77-112">HRESULT</span></span>|<span data-ttu-id="23c77-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="23c77-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="23c77-114">`EnumInterfaceImpls` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="23c77-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="23c77-115">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="23c77-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="23c77-116">В этом случае `pcImpls` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="23c77-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23c77-117">Требования</span><span class="sxs-lookup"><span data-stu-id="23c77-117">Requirements</span></span>  
 <span data-ttu-id="23c77-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c77-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c77-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23c77-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23c77-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23c77-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23c77-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c77-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c77-122">См. также</span><span class="sxs-lookup"><span data-stu-id="23c77-122">See also</span></span>
- [<span data-ttu-id="23c77-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="23c77-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="23c77-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="23c77-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
