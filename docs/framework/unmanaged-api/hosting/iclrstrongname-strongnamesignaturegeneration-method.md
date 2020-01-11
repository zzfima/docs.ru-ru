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
ms.openlocfilehash: ced7540afe931fb91240c770d76d205400157a51
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901104"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="83cc5-102">Метод ICLRStrongName::StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="83cc5-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="83cc5-103">Создает подпись строгого имени для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="83cc5-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83cc5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83cc5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="83cc5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83cc5-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="83cc5-106">окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="83cc5-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="83cc5-107">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="83cc5-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="83cc5-108">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="83cc5-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="83cc5-109">В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="83cc5-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="83cc5-110">Если `pbKeyBlob` не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="83cc5-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="83cc5-111">Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA).</span><span class="sxs-lookup"><span data-stu-id="83cc5-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="83cc5-112">В настоящее время не поддерживаются никакие другие типы ключей.</span><span class="sxs-lookup"><span data-stu-id="83cc5-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="83cc5-113">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="83cc5-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="83cc5-114">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="83cc5-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="83cc5-115">Если `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром `wszKeyContainer`, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="83cc5-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="83cc5-116">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="83cc5-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="83cc5-117">заполняет Указатель на расположение, в которое среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="83cc5-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="83cc5-118">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файле, указанном `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="83cc5-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="83cc5-119">Если `ppbSignatureBlob` не равно null, среда CLR выделяет пространство, в которое возвращается подпись.</span><span class="sxs-lookup"><span data-stu-id="83cc5-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="83cc5-120">Вызывающий объект должен освободить это пространство с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="83cc5-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="83cc5-121">заполняет Размер возвращенной сигнатуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="83cc5-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83cc5-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83cc5-122">Return Value</span></span>  
 <span data-ttu-id="83cc5-123">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="83cc5-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83cc5-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="83cc5-124">Remarks</span></span>  
 <span data-ttu-id="83cc5-125">Укажите значение NULL для `wszFilePath`, чтобы вычислить размер подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="83cc5-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="83cc5-126">Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="83cc5-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83cc5-127">Требования</span><span class="sxs-lookup"><span data-stu-id="83cc5-127">Requirements</span></span>  
 <span data-ttu-id="83cc5-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83cc5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83cc5-129">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="83cc5-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="83cc5-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83cc5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83cc5-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83cc5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cc5-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="83cc5-132">See also</span></span>

- [<span data-ttu-id="83cc5-133">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="83cc5-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="83cc5-134">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="83cc5-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
