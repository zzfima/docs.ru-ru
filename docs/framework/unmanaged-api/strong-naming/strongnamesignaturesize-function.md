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
ms.openlocfilehash: a8856790b655f071df704879a247169f456ae2f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130876"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="e81c9-102">Функция StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="e81c9-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="e81c9-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="e81c9-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="e81c9-104">`StrongNameSignatureSize` обычно используются компиляторами для определения объема пространства, резервируемого в файле при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="e81c9-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="e81c9-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="e81c9-105">This function has been deprecated.</span></span> <span data-ttu-id="e81c9-106">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e81c9-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81c9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e81c9-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="e81c9-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="e81c9-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="e81c9-109">окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="e81c9-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="e81c9-110">окне Размер `pbPublicKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="e81c9-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e81c9-111">окне Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="e81c9-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e81c9-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e81c9-112">Return Value</span></span>  
 <span data-ttu-id="e81c9-113">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e81c9-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e81c9-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="e81c9-114">Remarks</span></span>  
 <span data-ttu-id="e81c9-115">Если функция `StrongNameSignatureSize` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="e81c9-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81c9-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e81c9-116">Requirements</span></span>  
 <span data-ttu-id="e81c9-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e81c9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81c9-118">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e81c9-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e81c9-119">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e81c9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e81c9-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81c9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81c9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e81c9-121">See also</span></span>

- [<span data-ttu-id="e81c9-122">Метод StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="e81c9-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="e81c9-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e81c9-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
