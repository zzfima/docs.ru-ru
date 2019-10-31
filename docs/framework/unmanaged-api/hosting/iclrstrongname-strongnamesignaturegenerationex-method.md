---
title: Метод ICLRStrongName::StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
ms.openlocfilehash: 3ca11cfe948a53292de8e68d87e3e45816a18162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135001"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="86329-102">Метод ICLRStrongName::StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="86329-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="86329-103">Создает подпись строгого имени для указанной сборки в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="86329-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86329-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86329-104">Syntax</span></span>  
  
```cpp
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86329-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86329-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="86329-106">окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="86329-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="86329-107">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="86329-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="86329-108">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="86329-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="86329-109">В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="86329-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="86329-110">Если `pbKeyBlob` не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="86329-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="86329-111">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="86329-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="86329-112">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="86329-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="86329-113">Если `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром `wszKeyContainer`, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="86329-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="86329-114">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="86329-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="86329-115">заполняет Указатель на расположение, в которое среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="86329-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="86329-116">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файле, указанном `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="86329-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="86329-117">Если `ppbSignatureBlob` не равно null, среда CLR выделяет пространство, в которое возвращается подпись.</span><span class="sxs-lookup"><span data-stu-id="86329-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="86329-118">Вызывающий объект должен освободить это пространство с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="86329-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="86329-119">заполняет Размер возвращенной сигнатуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="86329-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="86329-120">окне Одно или несколько из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="86329-120">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="86329-121">`SN_SIGN_ALL_FILES` (0x00000001) — повторное вычисление всех хэшей для связанных модулей.</span><span class="sxs-lookup"><span data-stu-id="86329-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="86329-122">`SN_TEST_SIGN` (0x00000002) — Тестовая подпись сборки.</span><span class="sxs-lookup"><span data-stu-id="86329-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86329-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86329-123">Return Value</span></span>  
 <span data-ttu-id="86329-124">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="86329-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86329-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="86329-125">Remarks</span></span>  
 <span data-ttu-id="86329-126">Укажите значение NULL для `wszFilePath`, чтобы вычислить размер подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="86329-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="86329-127">Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="86329-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="86329-128">Если `SN_SIGN_ALL_FILES` указан, но открытый ключ не включен (как `pbKeyBlob`, так и `wszFilePath` равны NULL), хэши для связанных модулей пересчитываются, но сборка не подписывается повторно.</span><span class="sxs-lookup"><span data-stu-id="86329-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="86329-129">Если указан параметр `SN_TEST_SIGN`, заголовок среды CLR не изменяется, указывая, что сборка подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="86329-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86329-130">Требования</span><span class="sxs-lookup"><span data-stu-id="86329-130">Requirements</span></span>  
 <span data-ttu-id="86329-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86329-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86329-132">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="86329-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="86329-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="86329-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86329-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86329-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86329-135">См. также</span><span class="sxs-lookup"><span data-stu-id="86329-135">See also</span></span>

- [<span data-ttu-id="86329-136">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="86329-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="86329-137">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="86329-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
