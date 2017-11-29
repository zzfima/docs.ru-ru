---
title: "Метод ICLRStrongName::StrongNameGetBlob"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4ae90367cb84c97d5964ceb815943249af7b240
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="32f30-102">Метод ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="32f30-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="32f30-103">Заполняет указанный буфер двоичное представление исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="32f30-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32f30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32f30-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32f30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32f30-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="32f30-106">[in] Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="32f30-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="32f30-107">[in] Буфер, в которой для загрузки исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="32f30-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="32f30-108">[in, out] Максимальный размер в байтах, запрошена `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="32f30-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="32f30-109">По возвращении фактический размер в байтах для `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="32f30-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32f30-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32f30-110">Return Value</span></span>  
 <span data-ttu-id="32f30-111">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="32f30-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32f30-112">Требования</span><span class="sxs-lookup"><span data-stu-id="32f30-112">Requirements</span></span>  
 <span data-ttu-id="32f30-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32f30-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32f30-114">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="32f30-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="32f30-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32f30-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32f30-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32f30-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f30-117">См. также</span><span class="sxs-lookup"><span data-stu-id="32f30-117">See Also</span></span>  
 [<span data-ttu-id="32f30-118">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="32f30-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="32f30-119">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="32f30-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
