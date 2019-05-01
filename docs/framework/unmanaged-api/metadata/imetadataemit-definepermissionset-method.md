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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33eadccf691b14289a46ff460f3cef8ae636b129
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043983"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="75e67-102">Метод IMetaDataEmit::DefinePermissionSet</span><span class="sxs-lookup"><span data-stu-id="75e67-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="75e67-103">Создает определение набора разрешений с заданной подписью метаданных и получает маркер для этого определения набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="75e67-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75e67-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75e67-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75e67-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="75e67-106">[in] Объект, параметризация.</span><span class="sxs-lookup"><span data-stu-id="75e67-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="75e67-107">[in] Объект [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) значение, указывающее тип декларативной безопасности для использования.</span><span class="sxs-lookup"><span data-stu-id="75e67-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="75e67-108">[in] Разрешение BLOB-ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="75e67-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="75e67-109">[in] Размер в байтах из `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="75e67-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="75e67-110">[out] Токен, возвращенный разрешение.</span><span class="sxs-lookup"><span data-stu-id="75e67-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e67-111">Требования</span><span class="sxs-lookup"><span data-stu-id="75e67-111">Requirements</span></span>  
 <span data-ttu-id="75e67-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75e67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e67-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75e67-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75e67-114">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75e67-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75e67-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e67-116">См. также</span><span class="sxs-lookup"><span data-stu-id="75e67-116">See also</span></span>

- [<span data-ttu-id="75e67-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="75e67-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="75e67-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="75e67-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
