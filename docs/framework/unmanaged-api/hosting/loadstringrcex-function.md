---
title: Функция LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c942b9a94c83f5a3316cf3ae3ccbbad2b0ec69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="88118-102">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="88118-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="88118-103">Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="88118-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="88118-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88118-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88118-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88118-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="88118-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="88118-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="88118-107">[in] Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="88118-107">[in] A culture identifier.</span></span> <span data-ttu-id="88118-108">Передайте значение -1 `lcid` для использования с языком по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88118-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="88118-109">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="88118-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="88118-110">[out] Буфер, содержащий сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="88118-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="88118-111">[in] Размер буфера сообщений ошибок.</span><span class="sxs-lookup"><span data-stu-id="88118-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="88118-112">[in] Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="88118-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="88118-113">[out] Указатель на длину сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="88118-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88118-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88118-114">Return Value</span></span>  
 <span data-ttu-id="88118-115">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="88118-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="88118-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="88118-116">Return code</span></span>|<span data-ttu-id="88118-117">Описание</span><span class="sxs-lookup"><span data-stu-id="88118-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="88118-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="88118-118">S_OK</span></span>|<span data-ttu-id="88118-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="88118-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="88118-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="88118-120">E_INVALIDARG</span></span>|<span data-ttu-id="88118-121">`szBuffer` имеет значение null, или `iMax` равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="88118-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88118-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="88118-122">Remarks</span></span>  
 <span data-ttu-id="88118-123">Если метод завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="88118-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88118-124">Требования</span><span class="sxs-lookup"><span data-stu-id="88118-124">Requirements</span></span>  
 <span data-ttu-id="88118-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88118-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88118-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88118-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88118-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88118-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88118-128">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88118-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88118-129">См. также</span><span class="sxs-lookup"><span data-stu-id="88118-129">See Also</span></span>  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="88118-130">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="88118-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [<span data-ttu-id="88118-131">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="88118-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
