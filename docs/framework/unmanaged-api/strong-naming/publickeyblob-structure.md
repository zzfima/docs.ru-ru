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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140607"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="4adb8-102">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="4adb8-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="4adb8-103">Представляет в двоичном формате открытый ключ пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="4adb8-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4adb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4adb8-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="4adb8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4adb8-105">Members</span></span>  
  
|<span data-ttu-id="4adb8-106">Член</span><span class="sxs-lookup"><span data-stu-id="4adb8-106">Member</span></span>|<span data-ttu-id="4adb8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4adb8-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="4adb8-108">Идентификатор алгоритма подписи (типа `ALG_ID`, как определено в Винкрипт. h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="4adb8-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="4adb8-109">Идентификатор хэш-алгоритма (типа `ALG_ID`, как определено в Винкрипт. h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="4adb8-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="4adb8-110">Длина ключа в байтах.</span><span class="sxs-lookup"><span data-stu-id="4adb8-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="4adb8-111">Массив байтов переменной длины, который содержит значение ключа в формате, возвращенном CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="4adb8-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4adb8-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="4adb8-112">Remarks</span></span>  
 <span data-ttu-id="4adb8-113">Структура `PublicKeyBlob` используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="4adb8-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4adb8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4adb8-114">Requirements</span></span>  
 <span data-ttu-id="4adb8-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4adb8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4adb8-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="4adb8-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4adb8-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4adb8-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4adb8-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4adb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4adb8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4adb8-119">See also</span></span>

- [<span data-ttu-id="4adb8-120">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="4adb8-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="4adb8-121">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="4adb8-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
