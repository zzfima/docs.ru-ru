---
title: Метод ICLRStrongName::StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178042"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="8c7bd-102">Метод ICLRStrongName::StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="8c7bd-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="8c7bd-103">Создает подпись строгого имени для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c7bd-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c7bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c7bd-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8c7bd-106">(в) Путь к файлу, содержащий манифест сборки, для которого будет создана сильная подпись имени.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="8c7bd-107">(в) Название ключевого контейнера, содержащего публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="8c7bd-108">Если `pbKeyBlob` он `wszKeyContainer` недействителен, необходимо указать действительный контейнер в рамках поставщика криптографических услуг (CSP).</span><span class="sxs-lookup"><span data-stu-id="8c7bd-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="8c7bd-109">В этом случае пара ключей, хранящаяся в контейнере, используется для подписания файла.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="8c7bd-110">Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).</span><span class="sxs-lookup"><span data-stu-id="8c7bd-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="8c7bd-111">Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="8c7bd-112">В настоящее время никакие другие типы ключей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="8c7bd-113">(в) Указатель на публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="8c7bd-114">Эта пара находится в формате, `CryptExportKey` созданном функцией Win32.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="8c7bd-115">Если `pbKeyBlob` он недействителен, `wszKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="8c7bd-116">(в) Размер, в байтах, из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="8c7bd-117">(ваут) Указатель на место, к которому общее время выполнения языка возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="8c7bd-118">Если `ppbSignatureBlob` время выполнения является нулевым, время выполнения `wszFilePath`хранит подпись в файле, указанном .</span><span class="sxs-lookup"><span data-stu-id="8c7bd-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="8c7bd-119">Если `ppbSignatureBlob` время выполнения общего языка не является нулевым, то время выполнения общего языка выделяет пространство для возврата подписи.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="8c7bd-120">Звонящее должно освободить это пространство с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)</span><span class="sxs-lookup"><span data-stu-id="8c7bd-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="8c7bd-121">(ваут) Размер, в байтах, возвращенной подписи.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c7bd-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c7bd-122">Return Value</span></span>  
 <span data-ttu-id="8c7bd-123">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="8c7bd-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c7bd-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c7bd-124">Remarks</span></span>  
 <span data-ttu-id="8c7bd-125">Укажите `wszFilePath` нулевую для расчета размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="8c7bd-126">Подпись может храниться либо непосредственно в файле, либо возвращена вызывающему.</span><span class="sxs-lookup"><span data-stu-id="8c7bd-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c7bd-127">Требования</span><span class="sxs-lookup"><span data-stu-id="8c7bd-127">Requirements</span></span>  
 <span data-ttu-id="8c7bd-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c7bd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c7bd-129">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8c7bd-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8c7bd-130">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c7bd-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c7bd-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c7bd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7bd-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8c7bd-132">See also</span></span>

- [<span data-ttu-id="8c7bd-133">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="8c7bd-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="8c7bd-134">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8c7bd-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
