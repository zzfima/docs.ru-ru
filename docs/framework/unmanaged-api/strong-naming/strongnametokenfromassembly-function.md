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
ms.openlocfilehash: 71058a1ff82335b2a341904805d06738e662c296
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798873"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="c8a28-102">Функция StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="c8a28-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="c8a28-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="c8a28-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="c8a28-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="c8a28-104">This function has been deprecated.</span></span> <span data-ttu-id="c8a28-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c8a28-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8a28-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8a28-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8a28-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8a28-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c8a28-108">окне Путь к переносимому исполняемому файлу (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="c8a28-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c8a28-109">заполняет Возвращенный маркер строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c8a28-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c8a28-110">заполняет Размер (в байтах) маркера строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c8a28-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8a28-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c8a28-111">Return Value</span></span>  
 <span data-ttu-id="c8a28-112">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="c8a28-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8a28-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8a28-113">Remarks</span></span>  
 <span data-ttu-id="c8a28-114">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="c8a28-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c8a28-115">Маркер представляет собой 64-разрядный хэш, созданный из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="c8a28-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c8a28-116">Токен является частью строгого имени сборки и может быть считан из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="c8a28-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c8a28-117">После создания маркера необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="c8a28-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="c8a28-118">Если функция `StrongNameTokenFromAssembly` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="c8a28-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8a28-119">Требования</span><span class="sxs-lookup"><span data-stu-id="c8a28-119">Requirements</span></span>  
 <span data-ttu-id="c8a28-120">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8a28-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8a28-121">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c8a28-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c8a28-122">**Библиотечная** Включается в качестве ресурса в библиотеку Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c8a28-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="c8a28-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8a28-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a28-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c8a28-124">See also</span></span>

- [<span data-ttu-id="c8a28-125">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="c8a28-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="c8a28-126">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="c8a28-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="c8a28-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c8a28-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
