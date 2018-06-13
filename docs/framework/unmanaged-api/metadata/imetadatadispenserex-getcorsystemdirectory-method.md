---
title: Метод IMetaDataDispenserEx::GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf580f6d3fb18e729f3eca300aa817036eb61e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443434"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="1e31a-102">Метод IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="1e31a-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="1e31a-103">Возвращает каталог, содержащий текущий общеязыковая среда выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="1e31a-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="1e31a-104">Этот метод поддерживается только для использования в отладчиках out of process.</span><span class="sxs-lookup"><span data-stu-id="1e31a-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="1e31a-105">Если вызывается из другого компонента, возвращается значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1e31a-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e31a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e31a-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e31a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e31a-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="1e31a-108">[out] Буфер для получения имени каталога.</span><span class="sxs-lookup"><span data-stu-id="1e31a-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="1e31a-109">[in] Размер в байтах для `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="1e31a-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="1e31a-110">[out] Число байтов, фактически извлеченных в `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="1e31a-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e31a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1e31a-111">Requirements</span></span>  
 <span data-ttu-id="1e31a-112">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e31a-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e31a-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1e31a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e31a-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e31a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e31a-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e31a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e31a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1e31a-116">See Also</span></span>  
 [<span data-ttu-id="1e31a-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="1e31a-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="1e31a-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="1e31a-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
