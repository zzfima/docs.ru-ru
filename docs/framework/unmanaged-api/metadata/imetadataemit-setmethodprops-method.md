---
title: Метод IMetaDataEmit::SetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 1fb3f4486bc0ee7a85975770f94a8241999f10e0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442114"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="10e26-102">Метод IMetaDataEmit::SetMethodProps</span><span class="sxs-lookup"><span data-stu-id="10e26-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="10e26-103">Задает или обновляет компонент, хранящийся по указанному относительному виртуальному адресу метода, определенного в предыдущем вызове [IMetaDataEmit::D ефинемесод](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="10e26-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10e26-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10e26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10e26-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="10e26-106">окне Токен для изменяемого метода.</span><span class="sxs-lookup"><span data-stu-id="10e26-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="10e26-107">окне Атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="10e26-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="10e26-108">окне Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="10e26-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="10e26-109">окне Флаги реализации для метода.</span><span class="sxs-lookup"><span data-stu-id="10e26-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e26-110">Требования</span><span class="sxs-lookup"><span data-stu-id="10e26-110">Requirements</span></span>  
 <span data-ttu-id="10e26-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e26-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e26-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="10e26-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10e26-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="10e26-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10e26-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e26-115">См. также</span><span class="sxs-lookup"><span data-stu-id="10e26-115">See also</span></span>

- [<span data-ttu-id="10e26-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="10e26-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="10e26-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="10e26-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
