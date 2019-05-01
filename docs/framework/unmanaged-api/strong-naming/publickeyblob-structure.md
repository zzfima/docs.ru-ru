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
ms.openlocfilehash: 1a361e04b6f8f39ec0083471d8cb47d5a29376c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000354"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="33415-102">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="33415-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="33415-103">Представляет открытый ключ из пары открытого и закрытого ключей в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="33415-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33415-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33415-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="33415-105">Участники</span><span class="sxs-lookup"><span data-stu-id="33415-105">Members</span></span>  
  
|<span data-ttu-id="33415-106">Член</span><span class="sxs-lookup"><span data-stu-id="33415-106">Member</span></span>|<span data-ttu-id="33415-107">Описание</span><span class="sxs-lookup"><span data-stu-id="33415-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="33415-108">Идентификатор алгоритма подписи (типа `ALG_ID`, как определено в WinCrypt.h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="33415-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="33415-109">Идентификатор хэш-алгоритма (типа `ALG_ID`, как определено в WinCrypt.h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="33415-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="33415-110">Длина ключа в байтах.</span><span class="sxs-lookup"><span data-stu-id="33415-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="33415-111">Массив байтов переменной длины, содержащий значение ключа в формате, возвращенном CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="33415-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33415-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="33415-112">Remarks</span></span>  
 <span data-ttu-id="33415-113">`PublicKeyBlob` Структура используется [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)и другие функции строгого имени для представления открытый ключ из пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="33415-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33415-114">Требования</span><span class="sxs-lookup"><span data-stu-id="33415-114">Requirements</span></span>  
 <span data-ttu-id="33415-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33415-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33415-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="33415-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="33415-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33415-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33415-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33415-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33415-119">См. также</span><span class="sxs-lookup"><span data-stu-id="33415-119">See also</span></span>

- [<span data-ttu-id="33415-120">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="33415-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="33415-121">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="33415-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
