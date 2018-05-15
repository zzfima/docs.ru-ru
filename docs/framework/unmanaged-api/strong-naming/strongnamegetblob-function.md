---
title: Функция StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7892f87e4e4001dc6ba66a00becb0e7af2dc9cb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="a8863-102">Функция StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="a8863-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="a8863-103">Заполняет указанный буфер двоичное представление исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a8863-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="a8863-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="a8863-104">This function has been deprecated.</span></span> <span data-ttu-id="a8863-105">Используйте [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="a8863-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8863-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8863-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8863-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8863-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a8863-108">[in] Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="a8863-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="a8863-109">[in] Буфер, в которой для загрузки исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="a8863-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="a8863-110">[in, out] Максимальный размер в байтах, запрошена `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="a8863-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="a8863-111">По возвращении фактический размер в байтах для `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="a8863-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8863-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a8863-112">Return Value</span></span>  
 <span data-ttu-id="a8863-113">`true` При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="a8863-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8863-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8863-114">Remarks</span></span>  
 <span data-ttu-id="a8863-115">Если `StrongNameGetBlob` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="a8863-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8863-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a8863-116">Requirements</span></span>  
 <span data-ttu-id="a8863-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8863-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8863-118">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a8863-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a8863-119">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8863-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8863-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8863-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8863-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a8863-121">See Also</span></span>  
 [<span data-ttu-id="a8863-122">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="a8863-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="a8863-123">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="a8863-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="a8863-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a8863-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
