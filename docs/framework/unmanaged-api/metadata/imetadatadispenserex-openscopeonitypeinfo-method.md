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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218788"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="da2dc-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="da2dc-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="da2dc-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="da2dc-103">This method is not implemented.</span></span> <span data-ttu-id="da2dc-104">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da2dc-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2dc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da2dc-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2dc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="da2dc-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="da2dc-107">[in] Указатель на [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) интерфейс, который предоставляет сведения о типе, в котором требуется открыть область.</span><span class="sxs-lookup"><span data-stu-id="da2dc-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="da2dc-108">[in] Флаги для режима открытия.</span><span class="sxs-lookup"><span data-stu-id="da2dc-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="da2dc-109">[in] Необходимый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="da2dc-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="da2dc-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="da2dc-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2dc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="da2dc-111">Requirements</span></span>  
 <span data-ttu-id="da2dc-112">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2dc-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2dc-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="da2dc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da2dc-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da2dc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="da2dc-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da2dc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da2dc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="da2dc-116">See also</span></span>

- [<span data-ttu-id="da2dc-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="da2dc-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="da2dc-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="da2dc-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
