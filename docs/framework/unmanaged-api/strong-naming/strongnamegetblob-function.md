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
ms.openlocfilehash: e23232b55a841672ee193b980c310995ba688e00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160996"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="e7b58-102">Функция StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="e7b58-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="e7b58-103">Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="e7b58-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="e7b58-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="e7b58-104">This function has been deprecated.</span></span> <span data-ttu-id="e7b58-105">Используйте [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="e7b58-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b58-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7b58-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7b58-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7b58-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e7b58-108">[in] Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="e7b58-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="e7b58-109">[in] Буфер, в которой для загрузки исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="e7b58-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="e7b58-110">[in, out] Максимальный размер в байтах, запрошенную `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="e7b58-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="e7b58-111">По возвращении фактический размер в байтах из `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="e7b58-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7b58-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7b58-112">Return Value</span></span>  
 `true` <span data-ttu-id="e7b58-113">После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e7b58-113">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7b58-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7b58-114">Remarks</span></span>  
 <span data-ttu-id="e7b58-115">Если `StrongNameGetBlob` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="e7b58-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7b58-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e7b58-116">Requirements</span></span>  
 <span data-ttu-id="e7b58-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7b58-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7b58-118">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e7b58-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e7b58-119">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7b58-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e7b58-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e7b58-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7b58-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e7b58-121">See also</span></span>

- [<span data-ttu-id="e7b58-122">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="e7b58-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="e7b58-123">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="e7b58-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="e7b58-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e7b58-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
