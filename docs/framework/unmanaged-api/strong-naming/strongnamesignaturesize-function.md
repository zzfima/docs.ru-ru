---
title: Функция StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01c0f9ca0299e817618d93133c0eaca9fc63788e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767511"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="8b7ae-102">Функция StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="8b7ae-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="8b7ae-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="8b7ae-104">`StrongNameSignatureSize` обычно используется компиляторами, чтобы определить, какой объем места, резервируемого в файле, при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="8b7ae-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-105">This function has been deprecated.</span></span> <span data-ttu-id="8b7ae-106">Используйте [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b7ae-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b7ae-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8b7ae-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b7ae-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="8b7ae-109">[in] Структура типа [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащий открытую часть пары ключей, использованного для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="8b7ae-110">[in] Размер в байтах из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="8b7ae-111">[in] Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b7ae-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b7ae-112">Return Value</span></span>  
 <span data-ttu-id="8b7ae-113">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b7ae-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b7ae-114">Remarks</span></span>  
 <span data-ttu-id="8b7ae-115">Если `StrongNameSignatureSize` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b7ae-116">Требования</span><span class="sxs-lookup"><span data-stu-id="8b7ae-116">Requirements</span></span>  
 <span data-ttu-id="8b7ae-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b7ae-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b7ae-118">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8b7ae-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8b7ae-119">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b7ae-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b7ae-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b7ae-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b7ae-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8b7ae-121">See also</span></span>

- [<span data-ttu-id="8b7ae-122">Метод StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="8b7ae-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="8b7ae-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8b7ae-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
