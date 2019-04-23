---
title: Метод IMetaDataEmit::SetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82675af85f049aeb288b3dcc18f222c0387a37b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150401"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="27974-102">Метод IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="27974-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="27974-103">Задает сведения о маршалинге для параметра поля, возвращаемого значения метода или метода ссылается указанный токен PInvoke.</span><span class="sxs-lookup"><span data-stu-id="27974-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27974-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27974-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27974-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27974-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="27974-106">[in] Токен для целевого элемента данных.</span><span class="sxs-lookup"><span data-stu-id="27974-106">[in] The token for target data item.</span></span> <span data-ttu-id="27974-107">Это может быть либо `mdFieldDef` или `mdParamDef` токена.</span><span class="sxs-lookup"><span data-stu-id="27974-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="27974-108">[in] Сигнатура для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="27974-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="27974-109">[in] Число байт в `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="27974-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27974-110">Требования</span><span class="sxs-lookup"><span data-stu-id="27974-110">Requirements</span></span>  
 <span data-ttu-id="27974-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27974-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27974-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27974-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27974-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27974-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27974-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27974-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27974-115">См. также</span><span class="sxs-lookup"><span data-stu-id="27974-115">See also</span></span>

- [<span data-ttu-id="27974-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="27974-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="27974-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="27974-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
