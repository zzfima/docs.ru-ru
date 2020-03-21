---
title: Метод IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 6a4489d094974eb872b39824ceb185b0cbe48625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177831"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="eeb81-102">Метод IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="eeb81-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="eeb81-103">Перечисляет `mdAssemblyRef` экземпляры, определенные в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="eeb81-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eeb81-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeb81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eeb81-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="eeb81-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="eeb81-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="eeb81-107">Это должно быть нулевая величина, `EnumAssemblyRefs` когда метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="eeb81-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="eeb81-108">(ваут) Перечисление `mdAssemblyRef` токенов метаданных.</span><span class="sxs-lookup"><span data-stu-id="eeb81-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eeb81-109">(в) Максимальное количество токенов, которые могут `rAssemblyRefs` быть размещены в массиве.</span><span class="sxs-lookup"><span data-stu-id="eeb81-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="eeb81-110">(ваут) Количество токенов фактически помещено в `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="eeb81-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeb81-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eeb81-111">Return Value</span></span>  
  
|<span data-ttu-id="eeb81-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eeb81-112">HRESULT</span></span>|<span data-ttu-id="eeb81-113">Описание</span><span class="sxs-lookup"><span data-stu-id="eeb81-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="eeb81-114">`EnumAssemblyRefs`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="eeb81-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="eeb81-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="eeb81-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="eeb81-116">В этом `pcTokens` случае, устанавливается до нуля.</span><span class="sxs-lookup"><span data-stu-id="eeb81-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eeb81-117">Требования</span><span class="sxs-lookup"><span data-stu-id="eeb81-117">Requirements</span></span>  
 <span data-ttu-id="eeb81-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeb81-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb81-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eeb81-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eeb81-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eeb81-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eeb81-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb81-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb81-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eeb81-122">See also</span></span>

- [<span data-ttu-id="eeb81-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="eeb81-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
