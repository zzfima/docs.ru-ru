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
ms.openlocfilehash: 68332aee895f012bcf6ab6a72936c8dddc7f28a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122037"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="1a241-102">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="1a241-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="1a241-103">Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="1a241-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="1a241-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1a241-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a241-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a241-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a241-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a241-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="1a241-107">окне Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="1a241-107">[in] A culture identifier.</span></span> <span data-ttu-id="1a241-108">Pass-1 для `lcid` для использования языка и региональных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a241-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="1a241-109">окне Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1a241-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="1a241-110">заполняет Буфер, содержащий сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="1a241-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="1a241-111">окне Размер буфера сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1a241-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="1a241-112">окне Игнорируют.</span><span class="sxs-lookup"><span data-stu-id="1a241-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="1a241-113">заполняет Указатель на длину сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1a241-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a241-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a241-114">Return Value</span></span>  
 <span data-ttu-id="1a241-115">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="1a241-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1a241-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="1a241-116">Return code</span></span>|<span data-ttu-id="1a241-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1a241-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1a241-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a241-118">S_OK</span></span>|<span data-ttu-id="1a241-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="1a241-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="1a241-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1a241-120">E_INVALIDARG</span></span>|<span data-ttu-id="1a241-121">`szBuffer` имеет значение null или `iMax` равен нулю (0).</span><span class="sxs-lookup"><span data-stu-id="1a241-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a241-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="1a241-122">Remarks</span></span>  
 <span data-ttu-id="1a241-123">Если метод не завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="1a241-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a241-124">Требования</span><span class="sxs-lookup"><span data-stu-id="1a241-124">Requirements</span></span>  
 <span data-ttu-id="1a241-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a241-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a241-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1a241-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a241-127">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1a241-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a241-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a241-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a241-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1a241-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1a241-130">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="1a241-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="1a241-131">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="1a241-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
