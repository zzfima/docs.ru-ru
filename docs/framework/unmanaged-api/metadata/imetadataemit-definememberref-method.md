---
title: "Метод IMetaDataEmit::DefineMemberRef"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4dc4cd317e0e540aaa774cbf9c4c7a2a2ffa40be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="ec0db-102">Метод IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="ec0db-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="ec0db-103">Определяет ссылку на член модуля вне текущей области и получает маркер для этого определения ссылки.</span><span class="sxs-lookup"><span data-stu-id="ec0db-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec0db-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec0db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec0db-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="ec0db-106">[in] Токен для целевого члена класса или интерфейса, если элемент не является общим; Если элемент является глобальным, `mdModuleRef` маркера для этого другого файла.</span><span class="sxs-lookup"><span data-stu-id="ec0db-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="ec0db-107">[in] Имя целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="ec0db-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ec0db-108">[in] Сигнатура целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="ec0db-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ec0db-109">[in] Число байт в `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="ec0db-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="ec0db-110">[out] `mdMemberRef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="ec0db-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec0db-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ec0db-111">Requirements</span></span>  
 <span data-ttu-id="ec0db-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec0db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec0db-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec0db-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec0db-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec0db-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec0db-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec0db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0db-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ec0db-116">See Also</span></span>  
 [<span data-ttu-id="ec0db-117">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ec0db-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ec0db-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ec0db-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
