---
title: Метод IMetaDataEmit::DefinePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: e414bc5a7d537e8d153541f05b22dd91578e8739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177744"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="99be4-102">Метод IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="99be4-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="99be4-103">Устанавливает особенности подписи PInvoke метода, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="99be4-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99be4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99be4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99be4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99be4-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="99be4-106">(в) Токен для целевого метода.</span><span class="sxs-lookup"><span data-stu-id="99be4-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="99be4-107">(в) Флаги, используемые PInvoke для отображения.</span><span class="sxs-lookup"><span data-stu-id="99be4-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="99be4-108">(в) Название целевого метода экспорта в неуправляемом DLL.</span><span class="sxs-lookup"><span data-stu-id="99be4-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="99be4-109">(в) Токен для целевого родного DLL.</span><span class="sxs-lookup"><span data-stu-id="99be4-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99be4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="99be4-110">Requirements</span></span>  
 <span data-ttu-id="99be4-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99be4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99be4-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99be4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99be4-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99be4-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99be4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99be4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99be4-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99be4-115">See also</span></span>

- [<span data-ttu-id="99be4-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="99be4-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="99be4-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="99be4-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
