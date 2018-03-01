---
title: "Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45c65d0194ed44122a87dcd000359187fc020d0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="0adcc-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="0adcc-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="0adcc-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="0adcc-103">This method is not implemented.</span></span> <span data-ttu-id="0adcc-104">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0adcc-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0adcc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0adcc-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0adcc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0adcc-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="0adcc-107">[in] Указатель на [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) интерфейс, предоставляющий сведения о типе, в котором необходимо открыть область.</span><span class="sxs-lookup"><span data-stu-id="0adcc-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="0adcc-108">[in] Флаги для режима открытия.</span><span class="sxs-lookup"><span data-stu-id="0adcc-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="0adcc-109">[in] Нужного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0adcc-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="0adcc-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0adcc-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0adcc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0adcc-111">Requirements</span></span>  
 <span data-ttu-id="0adcc-112">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0adcc-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0adcc-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0adcc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0adcc-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0adcc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0adcc-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0adcc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0adcc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0adcc-116">See Also</span></span>  
 [<span data-ttu-id="0adcc-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="0adcc-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="0adcc-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="0adcc-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
