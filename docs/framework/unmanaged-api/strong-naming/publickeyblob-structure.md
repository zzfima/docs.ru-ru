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
ms.openlocfilehash: d7577a24a023c38370f5ac1f8c471ce31409e75d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459343"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="9acdd-102">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="9acdd-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="9acdd-103">Представляет открытый ключ из пары открытого и закрытого ключей в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="9acdd-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9acdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9acdd-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="9acdd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9acdd-105">Members</span></span>  
  
|<span data-ttu-id="9acdd-106">Член</span><span class="sxs-lookup"><span data-stu-id="9acdd-106">Member</span></span>|<span data-ttu-id="9acdd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9acdd-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="9acdd-108">Идентификатор алгоритма подписи (типа `ALG_ID`, как определено в WinCrypt.h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9acdd-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="9acdd-109">Идентификатор для хэш-алгоритм (типа `ALG_ID`, как определено в WinCrypt.h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9acdd-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="9acdd-110">Длина ключа в байтах.</span><span class="sxs-lookup"><span data-stu-id="9acdd-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="9acdd-111">Массив байтов переменной длины, содержащий значение ключа в формате, возвращенном CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="9acdd-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9acdd-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9acdd-112">Remarks</span></span>  
 <span data-ttu-id="9acdd-113">`PublicKeyBlob` Структура используется [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)и другие функции строгого имени, представляющих открытый ключ из пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9acdd-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9acdd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9acdd-114">Requirements</span></span>  
 <span data-ttu-id="9acdd-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9acdd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9acdd-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9acdd-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9acdd-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9acdd-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9acdd-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9acdd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9acdd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9acdd-119">See Also</span></span>  
 [<span data-ttu-id="9acdd-120">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="9acdd-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="9acdd-121">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="9acdd-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="9acdd-122">Структуры строгого именования</span><span class="sxs-lookup"><span data-stu-id="9acdd-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
