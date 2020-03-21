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
ms.openlocfilehash: e371330336002c673f2c54d882e70dbed41b743c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175841"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="9a06b-102">Метод IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="9a06b-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="9a06b-103">Определяет ссылку на участника модуля за пределами текущей области и получает маркер этого эталонного определения.</span><span class="sxs-lookup"><span data-stu-id="9a06b-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a06b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a06b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a06b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a06b-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="9a06b-106">(в) Токен для класса или интерфейса целевого участника, если участник не является глобальным; если участник является глобальным, `mdModuleRef` токен для другого файла.</span><span class="sxs-lookup"><span data-stu-id="9a06b-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="9a06b-107">(в) Имя целевого участника.</span><span class="sxs-lookup"><span data-stu-id="9a06b-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9a06b-108">(в) Подпись целевого члена.</span><span class="sxs-lookup"><span data-stu-id="9a06b-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9a06b-109">(в) Количество байтов `pvSigBlob`в .</span><span class="sxs-lookup"><span data-stu-id="9a06b-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="9a06b-110">(ваут) Назначенный `mdMemberRef` маркер.</span><span class="sxs-lookup"><span data-stu-id="9a06b-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a06b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9a06b-111">Requirements</span></span>  
 <span data-ttu-id="9a06b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a06b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a06b-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a06b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a06b-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a06b-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a06b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a06b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a06b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9a06b-116">See also</span></span>

- [<span data-ttu-id="9a06b-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9a06b-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9a06b-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9a06b-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
