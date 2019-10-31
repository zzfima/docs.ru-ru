---
title: Функция StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
ms.openlocfilehash: 7dd61be008ba08ca2b28ae3e7e8ff6326f8a41d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129237"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="762bb-102">Функция StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="762bb-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="762bb-103">Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="762bb-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="762bb-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="762bb-104">This function has been deprecated.</span></span> <span data-ttu-id="762bb-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="762bb-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="762bb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="762bb-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="762bb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="762bb-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="762bb-108">окне Путь к переносимому исполняемому файлу (DLL или exe), для которого проверяется сборка.</span><span class="sxs-lookup"><span data-stu-id="762bb-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="762bb-109">окне Флаги для изменения поведения проверки.</span><span class="sxs-lookup"><span data-stu-id="762bb-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="762bb-110">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="762bb-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="762bb-111">`SN_INFLAG_FORCE_VER` (0x00000001) — принудительная проверка, даже если необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="762bb-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="762bb-112">`SN_INFLAG_INSTALL` (0x00000002) — указывает, что это первый раз при проверке манифеста.</span><span class="sxs-lookup"><span data-stu-id="762bb-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="762bb-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) — указывает, что кэш будет разрешать доступ только тем пользователям, у которых есть права администратора.</span><span class="sxs-lookup"><span data-stu-id="762bb-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="762bb-114">`SN_INFLAG_USER_ACCESS` (0x00000008) — указывает, что сборка будет доступна только текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="762bb-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="762bb-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) — указывает, что кэш не предоставляет никаких гарантий ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="762bb-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="762bb-116">`SN_INFLAG_RUNTIME` (0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="762bb-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="762bb-117">заполняет Флаги, указывающие, была ли проверена подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="762bb-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="762bb-118">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="762bb-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="762bb-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) — это значение равно `false`, чтобы указать, что проверка прошла из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="762bb-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="762bb-120">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="762bb-120">Return Value</span></span>  
 <span data-ttu-id="762bb-121">`true`, если проверка прошла успешно; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="762bb-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="762bb-122">Требования</span><span class="sxs-lookup"><span data-stu-id="762bb-122">Requirements</span></span>  
 <span data-ttu-id="762bb-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="762bb-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="762bb-124">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="762bb-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="762bb-125">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="762bb-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="762bb-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="762bb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762bb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="762bb-127">See also</span></span>

- [<span data-ttu-id="762bb-128">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="762bb-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="762bb-129">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="762bb-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="762bb-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="762bb-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
