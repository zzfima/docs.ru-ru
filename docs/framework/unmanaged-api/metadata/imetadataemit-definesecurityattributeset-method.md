---
title: "Метод IMetaDataEmit::DefineSecurityAttributeSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineSecurityAttributeSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 79d5bb7240305d06d916e969765606ddc2ddf9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="c667b-102">Метод IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="c667b-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="c667b-103">Создает набор разрешений безопасности, чтобы присоединить объект, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="c667b-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c667b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c667b-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c667b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c667b-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="c667b-106">[in] Маркер, с которым необходимо связать сведения о безопасности.</span><span class="sxs-lookup"><span data-stu-id="c667b-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="c667b-107">[in] Массив `COR_SECATTR` структуры.</span><span class="sxs-lookup"><span data-stu-id="c667b-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="c667b-108">[in] Число элементов в `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="c667b-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="c667b-109">[out] При сбое метода, указывает индекс в `rSecAttrs` элемента, который вызвал проблему.</span><span class="sxs-lookup"><span data-stu-id="c667b-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c667b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c667b-110">Requirements</span></span>  
 <span data-ttu-id="c667b-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c667b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c667b-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c667b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c667b-113">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c667b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c667b-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c667b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c667b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c667b-115">See Also</span></span>  
 [<span data-ttu-id="c667b-116">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c667b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c667b-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c667b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
