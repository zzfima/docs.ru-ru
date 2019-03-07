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
ms.openlocfilehash: 46d8013d43dc14807804502e4a0820a2928f917e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499242"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="9d223-102">Функция StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="9d223-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="9d223-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="9d223-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="9d223-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9d223-104">This function has been deprecated.</span></span> <span data-ttu-id="9d223-105">Используйте [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9d223-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d223-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d223-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d223-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d223-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9d223-108">[in] Путь к переносимого исполняемого (PE) файла для сборки.</span><span class="sxs-lookup"><span data-stu-id="9d223-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="9d223-109">[out] Токен, возвращенный строгого имени.</span><span class="sxs-lookup"><span data-stu-id="9d223-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="9d223-110">[out] Размер в байтах, строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="9d223-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d223-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9d223-111">Return Value</span></span>  
 <span data-ttu-id="9d223-112">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9d223-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d223-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d223-113">Remarks</span></span>  
 <span data-ttu-id="9d223-114">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9d223-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="9d223-115">Токен является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="9d223-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="9d223-116">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="9d223-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="9d223-117">После создания маркера необходимо вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="9d223-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="9d223-118">Если `StrongNameTokenFromAssembly` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="9d223-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d223-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9d223-119">Requirements</span></span>  
 <span data-ttu-id="9d223-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d223-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d223-121">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9d223-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9d223-122">**Библиотека:** Включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9d223-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="9d223-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d223-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d223-124">См. также</span><span class="sxs-lookup"><span data-stu-id="9d223-124">See also</span></span>
- [<span data-ttu-id="9d223-125">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="9d223-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="9d223-126">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="9d223-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="9d223-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9d223-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
