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
ms.openlocfilehash: 12677799136e9ca887809e58fba838cb421ea183
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901064"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="175bd-102">Метод ICLRStrongName::StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="175bd-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="175bd-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="175bd-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="175bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="175bd-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="175bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="175bd-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="175bd-106">окне Путь к переносимому исполняемому файлу (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="175bd-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="175bd-107">заполняет Возвращенный маркер строгого имени.</span><span class="sxs-lookup"><span data-stu-id="175bd-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="175bd-108">заполняет Размер (в байтах) маркера строгого имени.</span><span class="sxs-lookup"><span data-stu-id="175bd-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="175bd-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="175bd-109">Return Value</span></span>  
 <span data-ttu-id="175bd-110">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="175bd-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="175bd-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="175bd-111">Remarks</span></span>  
 <span data-ttu-id="175bd-112">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="175bd-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="175bd-113">Маркер представляет собой 64-разрядный хэш, созданный из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="175bd-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="175bd-114">Токен является частью строгого имени сборки и может быть считан из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="175bd-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="175bd-115">После создания маркера следует вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="175bd-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="175bd-116">Требования</span><span class="sxs-lookup"><span data-stu-id="175bd-116">Requirements</span></span>  
 <span data-ttu-id="175bd-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="175bd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="175bd-118">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="175bd-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="175bd-119">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="175bd-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="175bd-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="175bd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175bd-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="175bd-121">See also</span></span>

- [<span data-ttu-id="175bd-122">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="175bd-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="175bd-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="175bd-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
