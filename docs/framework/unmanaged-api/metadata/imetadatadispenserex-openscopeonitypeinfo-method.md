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
ms.openlocfilehash: 60390fecad15dbb2c453453fa8c35556b5db6b54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777715"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="83e20-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="83e20-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="83e20-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="83e20-103">This method is not implemented.</span></span> <span data-ttu-id="83e20-104">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="83e20-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e20-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83e20-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83e20-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83e20-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="83e20-107">[in] Указатель на [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) интерфейс, который предоставляет сведения о типе, в котором требуется открыть область.</span><span class="sxs-lookup"><span data-stu-id="83e20-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="83e20-108">[in] Флаги для режима открытия.</span><span class="sxs-lookup"><span data-stu-id="83e20-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="83e20-109">[in] Необходимый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="83e20-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="83e20-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="83e20-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e20-111">Требования</span><span class="sxs-lookup"><span data-stu-id="83e20-111">Requirements</span></span>  
 <span data-ttu-id="83e20-112">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83e20-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e20-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="83e20-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83e20-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83e20-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83e20-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83e20-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e20-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83e20-116">See also</span></span>

- [<span data-ttu-id="83e20-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="83e20-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="83e20-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="83e20-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
