---
title: Метод ICLRStrongName::StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a2931c16e13d08c1e3e7d5b62e6583102a1b8cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984585"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="cef68-102">Метод ICLRStrongName::StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="cef68-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="cef68-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="cef68-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef68-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cef68-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cef68-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cef68-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cef68-106">[in] Путь к переносимого исполняемого (PE) файла для сборки.</span><span class="sxs-lookup"><span data-stu-id="cef68-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="cef68-107">[out] Токен, возвращенный строгого имени.</span><span class="sxs-lookup"><span data-stu-id="cef68-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="cef68-108">[out] Размер в байтах, строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="cef68-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cef68-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cef68-109">Return Value</span></span>  
 <span data-ttu-id="cef68-110">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="cef68-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cef68-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cef68-111">Remarks</span></span>  
 <span data-ttu-id="cef68-112">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="cef68-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="cef68-113">Токен является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="cef68-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="cef68-114">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="cef68-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="cef68-115">После создания маркера необходимо вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="cef68-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cef68-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cef68-116">Requirements</span></span>  
 <span data-ttu-id="cef68-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cef68-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cef68-118">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cef68-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cef68-119">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cef68-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cef68-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cef68-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef68-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cef68-121">See also</span></span>

- [<span data-ttu-id="cef68-122">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="cef68-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="cef68-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cef68-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
