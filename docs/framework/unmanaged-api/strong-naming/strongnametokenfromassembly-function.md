---
title: Функция StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f04d71e1709eed6c3a9f1af400f79b4722f4433
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457705"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="e6d38-102">Функция StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="e6d38-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="e6d38-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="e6d38-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="e6d38-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="e6d38-104">This function has been deprecated.</span></span> <span data-ttu-id="e6d38-105">Используйте [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="e6d38-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d38-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6d38-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6d38-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6d38-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e6d38-108">[in] Путь к файлу переносимого исполняемого (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="e6d38-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="e6d38-109">[out] Возвращаемый строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="e6d38-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="e6d38-110">[out] Размер в байтах строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="e6d38-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6d38-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e6d38-111">Return Value</span></span>  
 <span data-ttu-id="e6d38-112">`true` При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e6d38-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6d38-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6d38-113">Remarks</span></span>  
 <span data-ttu-id="e6d38-114">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e6d38-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="e6d38-115">Маркер является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="e6d38-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="e6d38-116">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="e6d38-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="e6d38-117">После создания маркера необходимо вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="e6d38-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="e6d38-118">Если `StrongNameTokenFromAssembly` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="e6d38-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d38-119">Требования</span><span class="sxs-lookup"><span data-stu-id="e6d38-119">Requirements</span></span>  
 <span data-ttu-id="e6d38-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6d38-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d38-121">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e6d38-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e6d38-122">**Библиотека:** включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e6d38-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="e6d38-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d38-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d38-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e6d38-124">See Also</span></span>  
 [<span data-ttu-id="e6d38-125">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="e6d38-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="e6d38-126">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="e6d38-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="e6d38-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e6d38-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
