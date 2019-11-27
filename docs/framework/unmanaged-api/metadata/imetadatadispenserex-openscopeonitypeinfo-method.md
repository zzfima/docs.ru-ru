---
title: Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 8deefe026e32a56d853e173e6a8fa3be942ccd9c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431132"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="22ec4-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="22ec4-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="22ec4-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="22ec4-103">This method is not implemented.</span></span> <span data-ttu-id="22ec4-104">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="22ec4-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ec4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22ec4-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ec4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="22ec4-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="22ec4-107">окне Указатель на интерфейс [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) , предоставляющий сведения о типе, в котором следует открыть область.</span><span class="sxs-lookup"><span data-stu-id="22ec4-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="22ec4-108">окне Флаги режима открытия.</span><span class="sxs-lookup"><span data-stu-id="22ec4-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="22ec4-109">окне Требуемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="22ec4-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="22ec4-110">заполняет Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="22ec4-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ec4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="22ec4-111">Requirements</span></span>  
 <span data-ttu-id="22ec4-112">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ec4-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ec4-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="22ec4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22ec4-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22ec4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22ec4-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ec4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ec4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="22ec4-116">See also</span></span>

- [<span data-ttu-id="22ec4-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="22ec4-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="22ec4-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="22ec4-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
