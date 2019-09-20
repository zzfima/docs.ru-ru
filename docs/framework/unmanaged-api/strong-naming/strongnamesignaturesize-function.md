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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798957"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="c5c12-102">Функция StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="c5c12-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="c5c12-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c5c12-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="c5c12-104">`StrongNameSignatureSize`обычно используется компиляторами для определения объема пространства, резервируемого в файле при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="c5c12-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="c5c12-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="c5c12-105">This function has been deprecated.</span></span> <span data-ttu-id="c5c12-106">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c5c12-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c12-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5c12-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c5c12-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5c12-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="c5c12-109">окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c5c12-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="c5c12-110">окне Размер (в байтах `pbPublicKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="c5c12-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="c5c12-111">окне Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c5c12-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5c12-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5c12-112">Return Value</span></span>  
 <span data-ttu-id="c5c12-113">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="c5c12-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5c12-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5c12-114">Remarks</span></span>  
 <span data-ttu-id="c5c12-115">Если функция `StrongNameSignatureSize` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="c5c12-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5c12-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c5c12-116">Requirements</span></span>  
 <span data-ttu-id="c5c12-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5c12-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5c12-118">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c5c12-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c5c12-119">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5c12-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5c12-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5c12-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c12-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c5c12-121">See also</span></span>

- [<span data-ttu-id="c5c12-122">Метод StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="c5c12-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="c5c12-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c5c12-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
