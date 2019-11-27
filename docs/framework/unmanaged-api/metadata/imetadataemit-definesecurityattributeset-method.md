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
ms.openlocfilehash: b98fab6c6127c3f78151d3b84160d4ca0434b6cd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428244"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="a6dab-102">Метод IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="a6dab-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="a6dab-103">Создает набор разрешений безопасности для присоединения к объекту, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="a6dab-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6dab-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6dab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6dab-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="a6dab-106">окне Токен, к которому присоединены сведения о безопасности.</span><span class="sxs-lookup"><span data-stu-id="a6dab-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="a6dab-107">окне Массив структур `COR_SECATTR`.</span><span class="sxs-lookup"><span data-stu-id="a6dab-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="a6dab-108">окне Число элементов в `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="a6dab-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="a6dab-109">заполняет В случае сбоя метода указывает индекс в `rSecAttrs` элемента, вызвавшего проблему.</span><span class="sxs-lookup"><span data-stu-id="a6dab-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6dab-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a6dab-110">Requirements</span></span>  
 <span data-ttu-id="a6dab-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6dab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6dab-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a6dab-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6dab-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a6dab-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6dab-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6dab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dab-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6dab-115">See also</span></span>

- [<span data-ttu-id="a6dab-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a6dab-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a6dab-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a6dab-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
