---
title: Структура PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e66196e2bd2cb326ca3f5badc67bcf8d81e5fc3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799161"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="dc103-102">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="dc103-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="dc103-103">Представляет в двоичном формате открытый ключ пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="dc103-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc103-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc103-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="dc103-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dc103-105">Members</span></span>  
  
|<span data-ttu-id="dc103-106">Член</span><span class="sxs-lookup"><span data-stu-id="dc103-106">Member</span></span>|<span data-ttu-id="dc103-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dc103-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="dc103-108">Идентификатор для алгоритма подписи (типа `ALG_ID`, как определено в винкрипт. h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="dc103-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="dc103-109">Идентификатор для хэш-алгоритма (типа `ALG_ID`, как определено в винкрипт. h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="dc103-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="dc103-110">Длина ключа в байтах.</span><span class="sxs-lookup"><span data-stu-id="dc103-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="dc103-111">Массив байтов переменной длины, который содержит значение ключа в формате, возвращенном CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="dc103-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc103-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc103-112">Remarks</span></span>  
 <span data-ttu-id="dc103-113">Структура `PublicKeyBlob` используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="dc103-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc103-114">Требования</span><span class="sxs-lookup"><span data-stu-id="dc103-114">Requirements</span></span>  
 <span data-ttu-id="dc103-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc103-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc103-116">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="dc103-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dc103-117">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc103-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc103-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc103-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc103-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dc103-119">See also</span></span>

- [<span data-ttu-id="dc103-120">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="dc103-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="dc103-121">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="dc103-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
