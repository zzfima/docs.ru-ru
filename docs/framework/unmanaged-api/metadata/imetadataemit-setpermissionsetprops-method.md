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
ms.openlocfilehash: 53a75b8e7edd15cd233577e0a3714fb5d981495f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432327"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="a8353-102">Метод IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="a8353-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="a8353-103">Задает или обновляет функции сигнатуры метаданных набора разрешений, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинепермиссионсет](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="a8353-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8353-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8353-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8353-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8353-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a8353-106">окне Токен метаданных, представляющий объект для декорирования.</span><span class="sxs-lookup"><span data-stu-id="a8353-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="a8353-107">окне Значение [кордеклсекурити](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) , указывающее тип используемой декларативной безопасности.</span><span class="sxs-lookup"><span data-stu-id="a8353-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="a8353-108">окне Большой двоичный объект разрешений.</span><span class="sxs-lookup"><span data-stu-id="a8353-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="a8353-109">окне Размер `pvPermission`в байтах.</span><span class="sxs-lookup"><span data-stu-id="a8353-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="a8353-110">заполняет Маркер метаданных `mdPermission`, представляющий обновленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="a8353-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8353-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a8353-111">Requirements</span></span>  
 <span data-ttu-id="a8353-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8353-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8353-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a8353-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8353-114">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8353-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8353-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8353-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8353-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a8353-116">See also</span></span>

- [<span data-ttu-id="a8353-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a8353-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a8353-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a8353-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
