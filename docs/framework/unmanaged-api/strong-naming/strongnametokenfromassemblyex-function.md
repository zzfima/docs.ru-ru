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
ms.openlocfilehash: 20bafd0dfc455538292e47ca33508c251ad68614
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458179"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="da3fd-102">Функция StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="da3fd-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="da3fd-103">Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ, представляющий маркер.</span><span class="sxs-lookup"><span data-stu-id="da3fd-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="da3fd-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="da3fd-104">This function has been deprecated.</span></span> <span data-ttu-id="da3fd-105">Используйте [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="da3fd-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da3fd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da3fd-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da3fd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="da3fd-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="da3fd-108">[in] Путь к файлу переносимого исполняемого (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="da3fd-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="da3fd-109">[out] Возвращаемый строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="da3fd-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="da3fd-110">[out] Размер в байтах строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="da3fd-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="da3fd-111">[out] Возвращаемый открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="da3fd-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="da3fd-112">[out] Размер в байтах для открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="da3fd-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da3fd-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="da3fd-113">Return Value</span></span>  
 <span data-ttu-id="da3fd-114">`true` При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="da3fd-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da3fd-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="da3fd-115">Remarks</span></span>  
 <span data-ttu-id="da3fd-116">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="da3fd-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="da3fd-117">Маркер является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="da3fd-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="da3fd-118">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="da3fd-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="da3fd-119">После получения ключа и создания маркера, необходимо вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="da3fd-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="da3fd-120">Если `StrongNameTokenFromAssemblyEx` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="da3fd-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da3fd-121">Требования</span><span class="sxs-lookup"><span data-stu-id="da3fd-121">Requirements</span></span>  
 <span data-ttu-id="da3fd-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da3fd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da3fd-123">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="da3fd-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="da3fd-124">**Библиотека:** включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="da3fd-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="da3fd-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da3fd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3fd-126">См. также</span><span class="sxs-lookup"><span data-stu-id="da3fd-126">See Also</span></span>  
 [<span data-ttu-id="da3fd-127">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="da3fd-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="da3fd-128">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="da3fd-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="da3fd-129">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="da3fd-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
