---
title: "Функция StrongNameGetBlobFromImage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetBlobFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameGetBlobFromImage
helpviewer_keywords: StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 423f874796320d1fbcda2ab642c71b7072642569
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="2ee10-102">Функция StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="2ee10-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="2ee10-103">Возвращает двоичное представление образа сборки по указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="2ee10-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="2ee10-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="2ee10-104">This function has been deprecated.</span></span> <span data-ttu-id="2ee10-105">Используйте [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="2ee10-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ee10-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ee10-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ee10-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ee10-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="2ee10-108">[in] Адрес памяти сопоставленных манифест.</span><span class="sxs-lookup"><span data-stu-id="2ee10-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2ee10-109">[in] Размер в байтах образа в `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="2ee10-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="2ee10-110">[in] Буфер, содержащий двоичное представление изображения.</span><span class="sxs-lookup"><span data-stu-id="2ee10-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="2ee10-111">[in, out] Максимальный размер в байтах, запрошена `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="2ee10-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="2ee10-112">По возвращении фактический размер в байтах для `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="2ee10-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ee10-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2ee10-113">Return Value</span></span>  
 <span data-ttu-id="2ee10-114">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="2ee10-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ee10-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ee10-115">Remarks</span></span>  
 <span data-ttu-id="2ee10-116">Если `StrongNameGetBlobFromImage` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="2ee10-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ee10-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2ee10-117">Requirements</span></span>  
 <span data-ttu-id="2ee10-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ee10-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ee10-119">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2ee10-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2ee10-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ee10-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ee10-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ee10-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee10-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2ee10-122">See Also</span></span>  
 [<span data-ttu-id="2ee10-123">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="2ee10-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="2ee10-124">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="2ee10-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="2ee10-125">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2ee10-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
