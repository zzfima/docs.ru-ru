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
ms.openlocfilehash: 4e11a52c977de7796043868e80c147d8cfd1f506
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431570"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="f266d-102">Метод IMetaDataEmit::DefinePermissionSet</span><span class="sxs-lookup"><span data-stu-id="f266d-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="f266d-103">Создает определение для набора разрешений с указанной сигнатурой метаданных и получает маркер для этого определения набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="f266d-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f266d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f266d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f266d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f266d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f266d-106">окне Объект для декорирования.</span><span class="sxs-lookup"><span data-stu-id="f266d-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="f266d-107">окне Значение [кордеклсекурити](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) , указывающее тип используемой декларативной безопасности.</span><span class="sxs-lookup"><span data-stu-id="f266d-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="f266d-108">окне Большой двоичный объект разрешений.</span><span class="sxs-lookup"><span data-stu-id="f266d-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="f266d-109">окне Размер `pvPermission`в байтах.</span><span class="sxs-lookup"><span data-stu-id="f266d-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="f266d-110">заполняет Возвращаемый маркер разрешения.</span><span class="sxs-lookup"><span data-stu-id="f266d-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f266d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f266d-111">Requirements</span></span>  
 <span data-ttu-id="f266d-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f266d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f266d-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f266d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f266d-114">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f266d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f266d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f266d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f266d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="f266d-116">See also</span></span>

- [<span data-ttu-id="f266d-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f266d-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f266d-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f266d-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
