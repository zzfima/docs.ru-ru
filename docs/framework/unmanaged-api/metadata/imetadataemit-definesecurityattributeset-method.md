---
title: Метод IMetaDataEmit::DefineSecurityAttributeSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 483f59ee3e81861ec1b05a0fee9c5db797aab68f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491157"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="50597-102">Метод IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="50597-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="50597-103">Создает набор разрешений безопасности для прикрепления к объекту, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="50597-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50597-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50597-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50597-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50597-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="50597-106">[in] Токен, к которому присоединен сведения о безопасности.</span><span class="sxs-lookup"><span data-stu-id="50597-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="50597-107">[in] Массив `COR_SECATTR` структуры.</span><span class="sxs-lookup"><span data-stu-id="50597-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="50597-108">[in] Число элементов в `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="50597-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="50597-109">[out] При сбое метода, указывает индекс в массиве `rSecAttrs` элемента, который вызвал проблему.</span><span class="sxs-lookup"><span data-stu-id="50597-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50597-110">Требования</span><span class="sxs-lookup"><span data-stu-id="50597-110">Requirements</span></span>  
 <span data-ttu-id="50597-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50597-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50597-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50597-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50597-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50597-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50597-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50597-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50597-115">См. также</span><span class="sxs-lookup"><span data-stu-id="50597-115">See also</span></span>
- [<span data-ttu-id="50597-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="50597-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="50597-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="50597-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
