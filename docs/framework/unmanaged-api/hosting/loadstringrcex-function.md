---
title: "Функция LoadStringRCEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRCEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRCEx
helpviewer_keywords: LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3467ebcd0b821c2313f3535c5b594ef664546e4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="8eaae-102">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="8eaae-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="8eaae-103">Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8eaae-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="8eaae-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8eaae-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eaae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8eaae-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8eaae-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8eaae-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="8eaae-107">[in] Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8eaae-107">[in] A culture identifier.</span></span> <span data-ttu-id="8eaae-108">Передайте значение -1 `lcid` для использования с языком по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8eaae-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="8eaae-109">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="8eaae-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="8eaae-110">[out] Буфер, содержащий сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="8eaae-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="8eaae-111">[in] Размер буфера сообщений ошибок.</span><span class="sxs-lookup"><span data-stu-id="8eaae-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="8eaae-112">[in] Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="8eaae-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="8eaae-113">[out] Указатель на длину сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="8eaae-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eaae-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8eaae-114">Return Value</span></span>  
 <span data-ttu-id="8eaae-115">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="8eaae-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="8eaae-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="8eaae-116">Return code</span></span>|<span data-ttu-id="8eaae-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8eaae-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="8eaae-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8eaae-118">S_OK</span></span>|<span data-ttu-id="8eaae-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8eaae-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="8eaae-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8eaae-120">E_INVALIDARG</span></span>|<span data-ttu-id="8eaae-121">`szBuffer`имеет значение null, или `iMax` равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="8eaae-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eaae-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="8eaae-122">Remarks</span></span>  
 <span data-ttu-id="8eaae-123">Если метод завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="8eaae-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eaae-124">Требования</span><span class="sxs-lookup"><span data-stu-id="8eaae-124">Requirements</span></span>  
 <span data-ttu-id="8eaae-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eaae-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eaae-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8eaae-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8eaae-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8eaae-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8eaae-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eaae-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eaae-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8eaae-129">See Also</span></span>  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="8eaae-130">Loadstringrc-функция</span><span class="sxs-lookup"><span data-stu-id="8eaae-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [<span data-ttu-id="8eaae-131">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="8eaae-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
