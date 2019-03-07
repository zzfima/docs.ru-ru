---
title: Функция LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e020b65966dc03bf326220ab0bab26bc61155c0c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485490"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="6acc7-102">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="6acc7-102">LoadStringRC Function</span></span>
<span data-ttu-id="6acc7-103">Преобразовывает значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.</span><span class="sxs-lookup"><span data-stu-id="6acc7-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="6acc7-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6acc7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acc7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6acc7-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6acc7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6acc7-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="6acc7-107">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="6acc7-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="6acc7-108">[out] Буфер, который содержит сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="6acc7-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="6acc7-109">[in] Размер буфера сообщений ошибок.</span><span class="sxs-lookup"><span data-stu-id="6acc7-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="6acc7-110">[in] Игнорируется.</span><span class="sxs-lookup"><span data-stu-id="6acc7-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6acc7-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6acc7-111">Return Value</span></span>  
 <span data-ttu-id="6acc7-112">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="6acc7-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="6acc7-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="6acc7-113">Return code</span></span>|<span data-ttu-id="6acc7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6acc7-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6acc7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="6acc7-115">S_OK</span></span>|<span data-ttu-id="6acc7-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="6acc7-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="6acc7-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6acc7-117">E_INVALIDARG</span></span>|<span data-ttu-id="6acc7-118">`szBuffer` имеет значение null или `iMax` равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="6acc7-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6acc7-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="6acc7-119">Remarks</span></span>  
 <span data-ttu-id="6acc7-120">Если метод завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="6acc7-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acc7-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6acc7-121">Requirements</span></span>  
 <span data-ttu-id="6acc7-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acc7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acc7-123">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6acc7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6acc7-124">**Библиотека:** Библиотек MSCorEE.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="6acc7-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="6acc7-125">Используйте библиотеку MSCorEE.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6acc7-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6acc7-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6acc7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acc7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6acc7-127">See also</span></span>
- [<span data-ttu-id="6acc7-128">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="6acc7-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="6acc7-129">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="6acc7-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
