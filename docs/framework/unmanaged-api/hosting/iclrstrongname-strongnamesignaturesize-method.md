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
ms.openlocfilehash: e789996af3aedd17251fc52cde52a336f65053ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176348"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="8c62e-102">Метод ICLRStrongName::StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="8c62e-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="8c62e-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="8c62e-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="8c62e-104">Этот метод обычно используется компиляторами для определения места для резервирования в файле при создании сборки, подписанной задержкой.</span><span class="sxs-lookup"><span data-stu-id="8c62e-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c62e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c62e-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="8c62e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c62e-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="8c62e-107">(в) Структура типа [PublicKeyBlob,](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) содержащая публичную часть ключевой пары, используемой для создания сильной подписи имен.</span><span class="sxs-lookup"><span data-stu-id="8c62e-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="8c62e-108">(в) Размер, в байтах, из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="8c62e-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="8c62e-109">(в) Количество байтов, необходимых для хранения сильной подписи имени.</span><span class="sxs-lookup"><span data-stu-id="8c62e-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c62e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c62e-110">Return Value</span></span>  
 <span data-ttu-id="8c62e-111">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="8c62e-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c62e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8c62e-112">Requirements</span></span>  
 <span data-ttu-id="8c62e-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c62e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c62e-114">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8c62e-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8c62e-115">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c62e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c62e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c62e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c62e-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8c62e-117">See also</span></span>

- [<span data-ttu-id="8c62e-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8c62e-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
