---
title: Функция StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799126"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="61199-102">Функция StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="61199-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="61199-103">Освобождает память, выделенную предыдущим вызовом функции строгого имени, такой как [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) или [StrongNameSignatureGeneration ](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="61199-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="61199-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="61199-104">This function has been deprecated.</span></span> <span data-ttu-id="61199-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="61199-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61199-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61199-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61199-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="61199-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="61199-108">окне Указатель на память для освобождения.</span><span class="sxs-lookup"><span data-stu-id="61199-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61199-109">Требования</span><span class="sxs-lookup"><span data-stu-id="61199-109">Requirements</span></span>  
 <span data-ttu-id="61199-110">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61199-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61199-111">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="61199-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="61199-112">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="61199-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61199-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61199-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61199-114">См. также</span><span class="sxs-lookup"><span data-stu-id="61199-114">See also</span></span>

- [<span data-ttu-id="61199-115">Метод StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="61199-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="61199-116">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="61199-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
