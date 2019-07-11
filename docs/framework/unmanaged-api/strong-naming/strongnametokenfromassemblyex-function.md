---
title: Функция StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14af44901e7c65933800e41328e95602ce715282
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783180"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="f1d45-102">Функция StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="f1d45-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="f1d45-103">Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ, представляющий токен.</span><span class="sxs-lookup"><span data-stu-id="f1d45-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="f1d45-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="f1d45-104">This function has been deprecated.</span></span> <span data-ttu-id="f1d45-105">Используйте [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f1d45-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d45-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1d45-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1d45-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1d45-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f1d45-108">[in] Путь к переносимого исполняемого (PE) файла для сборки.</span><span class="sxs-lookup"><span data-stu-id="f1d45-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="f1d45-109">[out] Токен, возвращенный строгого имени.</span><span class="sxs-lookup"><span data-stu-id="f1d45-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="f1d45-110">[out] Размер в байтах, строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="f1d45-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f1d45-111">[out] Возвращаемый открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="f1d45-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f1d45-112">[out] Размер в байтах, открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="f1d45-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1d45-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1d45-113">Return Value</span></span>  
 <span data-ttu-id="f1d45-114">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="f1d45-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d45-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1d45-115">Remarks</span></span>  
 <span data-ttu-id="f1d45-116">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="f1d45-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="f1d45-117">Токен является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="f1d45-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="f1d45-118">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="f1d45-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="f1d45-119">После извлечения ключа и создания маркера, необходимо вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="f1d45-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="f1d45-120">Если `StrongNameTokenFromAssemblyEx` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="f1d45-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d45-121">Требования</span><span class="sxs-lookup"><span data-stu-id="f1d45-121">Requirements</span></span>  
 <span data-ttu-id="f1d45-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d45-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d45-123">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f1d45-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f1d45-124">**Библиотека:** Включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f1d45-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f1d45-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d45-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d45-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f1d45-126">See also</span></span>

- [<span data-ttu-id="f1d45-127">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="f1d45-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="f1d45-128">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="f1d45-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="f1d45-129">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f1d45-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
