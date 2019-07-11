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
ms.openlocfilehash: f03a2dfa60f2fbdce317d96a9e5b23c6f017dc3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777741"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="ec6dc-102">Метод IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="ec6dc-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="ec6dc-103">Получает каталог, содержащий текущий среда CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="ec6dc-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="ec6dc-104">Этот метод поддерживается только для использования вне процесса отладки.</span><span class="sxs-lookup"><span data-stu-id="ec6dc-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="ec6dc-105">Если вызывается из другого компонента, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ec6dc-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6dc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec6dc-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec6dc-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec6dc-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="ec6dc-108">[out] Буфер для получения имени каталога.</span><span class="sxs-lookup"><span data-stu-id="ec6dc-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ec6dc-109">[in] Размер в байтах из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ec6dc-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="ec6dc-110">[out] Число байтов, фактически возвращенных в `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ec6dc-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec6dc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ec6dc-111">Requirements</span></span>  
 <span data-ttu-id="ec6dc-112">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec6dc-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec6dc-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec6dc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec6dc-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec6dc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec6dc-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec6dc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6dc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ec6dc-116">See also</span></span>

- [<span data-ttu-id="ec6dc-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="ec6dc-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="ec6dc-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="ec6dc-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
