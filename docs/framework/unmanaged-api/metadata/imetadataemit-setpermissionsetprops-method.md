---
title: Метод IMetaDataEmit::SetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177490"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="63d5c-102">Метод IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="63d5c-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="63d5c-103">Устанавливает или обновляет функции подписи метаданных разрешения, определенного предыдущим вызовом на [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="63d5c-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63d5c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63d5c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="63d5c-106">(в) Токен метаданных, представляющий объект, который должен быть оформлен.</span><span class="sxs-lookup"><span data-stu-id="63d5c-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="63d5c-107">(в) Значение [CorDeclSecurity,](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) которое определяет тип декларативной безопасности, которая будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="63d5c-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="63d5c-108">(в) Разрешение BLOB.</span><span class="sxs-lookup"><span data-stu-id="63d5c-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="63d5c-109">(в) Размер, в байтах, из `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="63d5c-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="63d5c-110">(ваут) Токен `mdPermission` метаданных, представляющий обновленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="63d5c-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d5c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="63d5c-111">Requirements</span></span>  
 <span data-ttu-id="63d5c-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d5c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d5c-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="63d5c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63d5c-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63d5c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63d5c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d5c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d5c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="63d5c-116">See also</span></span>

- [<span data-ttu-id="63d5c-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="63d5c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="63d5c-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="63d5c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
