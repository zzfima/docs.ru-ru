---
title: Функция StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176894"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="ac8e0-102">Функция StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="ac8e0-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="ac8e0-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="ac8e0-104">`StrongNameSignatureSize`обычно используется компиляторами для определения места для резервирования в файле при создании сборки, подписанной задержкой.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="ac8e0-105">Эта функция была амортизирована.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-105">This function has been deprecated.</span></span> <span data-ttu-id="ac8e0-106">Вместо этого используйте метод [ICLRStrongName::StrongNameSignatureSize.](../hosting/iclrstrongname-strongnamesignaturesize-method.md)</span><span class="sxs-lookup"><span data-stu-id="ac8e0-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac8e0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac8e0-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="ac8e0-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac8e0-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="ac8e0-109">(в) Структура типа [PublicKeyBlob,](publickeyblob-structure.md) содержащая публичную часть ключевой пары, используемой для создания сильной подписи имен.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="ac8e0-110">(в) Размер, в байтах, из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="ac8e0-111">(в) Количество байтов, необходимых для хранения сильной подписи имени.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac8e0-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac8e0-112">Return Value</span></span>  
 <span data-ttu-id="ac8e0-113">`true`при успешном завершении; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="ac8e0-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac8e0-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac8e0-114">Remarks</span></span>  
 <span data-ttu-id="ac8e0-115">Если `StrongNameSignatureSize` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac8e0-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ac8e0-116">Requirements</span></span>  
 <span data-ttu-id="ac8e0-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac8e0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac8e0-118">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ac8e0-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ac8e0-119">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac8e0-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac8e0-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac8e0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac8e0-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ac8e0-121">See also</span></span>

- [<span data-ttu-id="ac8e0-122">Метод StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="ac8e0-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="ac8e0-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ac8e0-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
