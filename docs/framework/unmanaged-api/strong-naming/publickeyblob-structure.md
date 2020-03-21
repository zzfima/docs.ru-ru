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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176959"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="ca201-102">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="ca201-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="ca201-103">Представляет, в двоичном формате, открытый ключ публичной/ частной ключевой пары.</span><span class="sxs-lookup"><span data-stu-id="ca201-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca201-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca201-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="ca201-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ca201-105">Members</span></span>  
  
|<span data-ttu-id="ca201-106">Участник</span><span class="sxs-lookup"><span data-stu-id="ca201-106">Member</span></span>|<span data-ttu-id="ca201-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ca201-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="ca201-108">Идентификатор алгоритма подписи (типа, `ALG_ID`как это определено в WinCrypt.h) общедоступного ключа.</span><span class="sxs-lookup"><span data-stu-id="ca201-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="ca201-109">Идентификатор алгоритма хэша (типа, `ALG_ID`как это определено в WinCrypt.h) общедоступного ключа.</span><span class="sxs-lookup"><span data-stu-id="ca201-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="ca201-110">Длина ключа в байтах.</span><span class="sxs-lookup"><span data-stu-id="ca201-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="ca201-111">Массив байт с переменной длиной, содержащий ключевое значение в формате, возвращенном CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="ca201-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca201-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca201-112">Remarks</span></span>  
 <span data-ttu-id="ca201-113">Структура `PublicKeyBlob` используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), и другие сильные функции имя представлять общественный ключ от публичного / частного ключа пары.</span><span class="sxs-lookup"><span data-stu-id="ca201-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca201-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ca201-114">Requirements</span></span>  
 <span data-ttu-id="ca201-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca201-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca201-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ca201-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ca201-117">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca201-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca201-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca201-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca201-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca201-119">See also</span></span>

- [<span data-ttu-id="ca201-120">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="ca201-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="ca201-121">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="ca201-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
