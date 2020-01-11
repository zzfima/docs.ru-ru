---
title: Метод ICLRStrongName::StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: 049324baec02fbb03c2db80391ade8a24920a15c
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901082"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="8b349-102">Метод ICLRStrongName::StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="8b349-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="8b349-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8b349-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="8b349-104">Этот метод обычно используется компиляторами для определения объема пространства, резервируемого в файле при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="8b349-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b349-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b349-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8b349-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b349-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="8b349-107">окне Структура типа [публиккэйблоб](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8b349-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="8b349-108">окне Размер `pbPublicKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="8b349-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="8b349-109">окне Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8b349-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b349-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b349-110">Return Value</span></span>  
 <span data-ttu-id="8b349-111">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="8b349-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b349-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8b349-112">Requirements</span></span>  
 <span data-ttu-id="8b349-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b349-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b349-114">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8b349-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8b349-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8b349-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b349-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b349-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b349-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b349-117">See also</span></span>

- [<span data-ttu-id="8b349-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8b349-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
