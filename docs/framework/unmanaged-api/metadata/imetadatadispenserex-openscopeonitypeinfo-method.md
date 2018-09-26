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
ms.openlocfilehash: d5fd96f390b0bba60d1b95d20273bbf670208d41
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108544"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="7e4b8-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="7e4b8-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="7e4b8-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="7e4b8-103">This method is not implemented.</span></span> <span data-ttu-id="7e4b8-104">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="7e4b8-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4b8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e4b8-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e4b8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e4b8-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="7e4b8-107">[in] Указатель на [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) интерфейс, который предоставляет сведения о типе, в котором требуется открыть область.</span><span class="sxs-lookup"><span data-stu-id="7e4b8-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="7e4b8-108">[in] Флаги для режима открытия.</span><span class="sxs-lookup"><span data-stu-id="7e4b8-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="7e4b8-109">[in] Необходимый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7e4b8-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="7e4b8-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7e4b8-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e4b8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7e4b8-111">Requirements</span></span>  
 <span data-ttu-id="7e4b8-112">**Платформа:** см. в разделе [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e4b8-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e4b8-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e4b8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e4b8-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e4b8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e4b8-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e4b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4b8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7e4b8-116">See Also</span></span>  
 [<span data-ttu-id="7e4b8-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="7e4b8-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="7e4b8-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="7e4b8-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
