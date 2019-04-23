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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: deecd9ed4161bbd72e97a6320188961ae76d1e7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218788"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="4b5bb-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="4b5bb-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="4b5bb-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="4b5bb-103">This method is not implemented.</span></span> <span data-ttu-id="4b5bb-104">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="4b5bb-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5bb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b5bb-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b5bb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b5bb-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="4b5bb-107">[in] Указатель на [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) интерфейс, который предоставляет сведения о типе, в котором требуется открыть область.</span><span class="sxs-lookup"><span data-stu-id="4b5bb-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="4b5bb-108">[in] Флаги для режима открытия.</span><span class="sxs-lookup"><span data-stu-id="4b5bb-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="4b5bb-109">[in] Необходимый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4b5bb-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="4b5bb-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4b5bb-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b5bb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4b5bb-111">Requirements</span></span>  
 <span data-ttu-id="4b5bb-112">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b5bb-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b5bb-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b5bb-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b5bb-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b5bb-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b5bb-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b5bb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5bb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4b5bb-116">See also</span></span>

- [<span data-ttu-id="4b5bb-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="4b5bb-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="4b5bb-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="4b5bb-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
