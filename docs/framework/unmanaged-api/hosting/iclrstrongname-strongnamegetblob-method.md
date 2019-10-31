---
title: Метод ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 9d7f1a71658b53a1b4167c767eb89c873308421b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135128"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="8b674-102">Метод ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="8b674-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="8b674-103">Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="8b674-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b674-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b674-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b674-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b674-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8b674-106">окне Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="8b674-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="8b674-107">окне Буфер, в который загружается исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="8b674-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="8b674-108">[вход, выход] Запрошенный максимальный размер `pbBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="8b674-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="8b674-109">При возврате фактический размер (в байтах) `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="8b674-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b674-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b674-110">Return Value</span></span>  
 <span data-ttu-id="8b674-111">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="8b674-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b674-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8b674-112">Requirements</span></span>  
 <span data-ttu-id="8b674-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b674-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b674-114">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8b674-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8b674-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8b674-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b674-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b674-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b674-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8b674-117">See also</span></span>

- [<span data-ttu-id="8b674-118">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="8b674-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="8b674-119">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8b674-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
