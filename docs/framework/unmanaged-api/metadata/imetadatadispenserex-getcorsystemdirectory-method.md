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
ms.openlocfilehash: bb61dbcee1851ebe70c1dc0138e14aaa7a08d901
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468693"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="d4312-102">Метод IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="d4312-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="d4312-103">Получает каталог, содержащий текущий среда CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="d4312-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="d4312-104">Этот метод поддерживается только для использования вне процесса отладки.</span><span class="sxs-lookup"><span data-stu-id="d4312-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="d4312-105">Если вызывается из другого компонента, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="d4312-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4312-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4312-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4312-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4312-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="d4312-108">[out] Буфер для получения имени каталога.</span><span class="sxs-lookup"><span data-stu-id="d4312-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d4312-109">[in] Размер в байтах из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="d4312-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="d4312-110">[out] Число байтов, фактически возвращенных в `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="d4312-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4312-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d4312-111">Requirements</span></span>  
 <span data-ttu-id="d4312-112">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4312-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4312-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d4312-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4312-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4312-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4312-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4312-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4312-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d4312-116">See also</span></span>
- [<span data-ttu-id="d4312-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d4312-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="d4312-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="d4312-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
