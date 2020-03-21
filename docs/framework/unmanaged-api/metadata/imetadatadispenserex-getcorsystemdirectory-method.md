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
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175919"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="61722-102">Метод IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="61722-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="61722-103">Получает каталог, в котором содержится текущее время выполнения общего языка (CLR).</span><span class="sxs-lookup"><span data-stu-id="61722-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="61722-104">Этот метод поддерживается только для использования внепроцессными отладчиками.</span><span class="sxs-lookup"><span data-stu-id="61722-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="61722-105">Если вызов из другого компонента, он вернется E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="61722-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61722-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61722-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61722-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="61722-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="61722-108">(ваут) Буфер для получения имени каталога.</span><span class="sxs-lookup"><span data-stu-id="61722-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="61722-109">(в) Размер, в байтах, из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="61722-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="61722-110">(ваут) Количество байтов фактически `szBuffer`вернулся в .</span><span class="sxs-lookup"><span data-stu-id="61722-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61722-111">Требования</span><span class="sxs-lookup"><span data-stu-id="61722-111">Requirements</span></span>  
 <span data-ttu-id="61722-112">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61722-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61722-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61722-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61722-114">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61722-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61722-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61722-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61722-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61722-116">See also</span></span>

- [<span data-ttu-id="61722-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="61722-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="61722-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="61722-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
