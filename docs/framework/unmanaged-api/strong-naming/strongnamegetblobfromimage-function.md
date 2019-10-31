---
title: Функция StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 41226cd909900bd2da7bdcf9b9a49567d3042b01
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094878"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="62f6b-102">Функция StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="62f6b-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="62f6b-103">Получает двоичное представление образа сборки по указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="62f6b-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="62f6b-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="62f6b-104">This function has been deprecated.</span></span> <span data-ttu-id="62f6b-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) .</span><span class="sxs-lookup"><span data-stu-id="62f6b-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f6b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62f6b-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62f6b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="62f6b-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="62f6b-108">окне Адрес сопоставленного манифеста сборки в памяти.</span><span class="sxs-lookup"><span data-stu-id="62f6b-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="62f6b-109">окне Размер изображения в байтах, в `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="62f6b-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="62f6b-110">окне Буфер для хранения двоичного представления изображения.</span><span class="sxs-lookup"><span data-stu-id="62f6b-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="62f6b-111">[вход, выход] Запрошенный максимальный размер `pbBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="62f6b-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="62f6b-112">При возврате фактический размер (в байтах) `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="62f6b-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62f6b-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="62f6b-113">Return Value</span></span>  
 <span data-ttu-id="62f6b-114">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="62f6b-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62f6b-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="62f6b-115">Remarks</span></span>  
 <span data-ttu-id="62f6b-116">Если функция `StrongNameGetBlobFromImage` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="62f6b-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f6b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="62f6b-117">Requirements</span></span>  
 <span data-ttu-id="62f6b-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62f6b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f6b-119">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="62f6b-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="62f6b-120">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62f6b-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62f6b-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62f6b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f6b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="62f6b-122">See also</span></span>

- [<span data-ttu-id="62f6b-123">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="62f6b-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="62f6b-124">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="62f6b-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="62f6b-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="62f6b-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
