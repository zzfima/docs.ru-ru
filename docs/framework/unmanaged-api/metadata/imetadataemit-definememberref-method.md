---
title: Метод IMetaDataEmit::DefineMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5d386b1d3f95e703cc5d9ad1353ea6b84b5b455
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176050"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="177f5-102">Метод IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="177f5-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="177f5-103">Определяет ссылку на член модуля вне текущей области и получает маркер для этого определения ссылки.</span><span class="sxs-lookup"><span data-stu-id="177f5-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="177f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="177f5-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="177f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="177f5-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="177f5-106">[in] Маркер для целевого члена класса или интерфейса, если элемент не является общим; Если элемент является глобальным, `mdModuleRef` маркеров для других файла.</span><span class="sxs-lookup"><span data-stu-id="177f5-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="177f5-107">[in] Имя целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="177f5-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="177f5-108">[in] Сигнатура целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="177f5-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="177f5-109">[in] Число байт в `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="177f5-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="177f5-110">[out] `mdMemberRef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="177f5-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="177f5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="177f5-111">Requirements</span></span>  
 <span data-ttu-id="177f5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="177f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="177f5-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="177f5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="177f5-114">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="177f5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="177f5-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="177f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="177f5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="177f5-116">See also</span></span>

- [<span data-ttu-id="177f5-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="177f5-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="177f5-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="177f5-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
