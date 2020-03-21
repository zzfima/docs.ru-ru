---
title: Метод IMetaDataEmit::DefinePermissionSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175802"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="4c95c-102">Метод IMetaDataEmit::DefinePermissionSet</span><span class="sxs-lookup"><span data-stu-id="4c95c-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="4c95c-103">Создает определение для набора разрешений с указанной подписью метаданных и получает маркер к этому определению, установленного для разрешения.</span><span class="sxs-lookup"><span data-stu-id="4c95c-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c95c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c95c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c95c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c95c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="4c95c-106">(в) Объект, который будет украшен.</span><span class="sxs-lookup"><span data-stu-id="4c95c-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="4c95c-107">(в) Значение [CorDeclSecurity,](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) которое определяет тип декларативной безопасности, которая будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="4c95c-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="4c95c-108">(в) Разрешение BLOB.</span><span class="sxs-lookup"><span data-stu-id="4c95c-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="4c95c-109">(в) Размер, в байтах, из `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="4c95c-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="4c95c-110">(ваут) Токен разрешения возвращен.</span><span class="sxs-lookup"><span data-stu-id="4c95c-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c95c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4c95c-111">Requirements</span></span>  
 <span data-ttu-id="4c95c-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c95c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c95c-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4c95c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c95c-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c95c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c95c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c95c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c95c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c95c-116">See also</span></span>

- [<span data-ttu-id="4c95c-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4c95c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4c95c-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4c95c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
