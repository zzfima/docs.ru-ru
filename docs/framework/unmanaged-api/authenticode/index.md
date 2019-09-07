---
title: Authenticode (справочник по неуправляемым интерфейсам API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2c0163d03a19a7bc00ae705fd633ef4f0880082
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776553"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="18e9a-102">Authenticode (справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="18e9a-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="18e9a-103">Поддерживает модуль создания и проверки лицензий Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="18e9a-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18e9a-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="18e9a-104">In This Section</span></span>  
 [<span data-ttu-id="18e9a-105">Функция _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="18e9a-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="18e9a-106">Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.</span><span class="sxs-lookup"><span data-stu-id="18e9a-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="18e9a-107">Функция _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="18e9a-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="18e9a-108">Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="18e9a-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="18e9a-109">Функция _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="18e9a-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="18e9a-110">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="18e9a-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="18e9a-111">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="18e9a-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="18e9a-112">Освобождает ресурсы, выделенные для структуры AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="18e9a-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="18e9a-113">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="18e9a-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="18e9a-114">Освобождает ресурсы, выделенные для структуры AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="18e9a-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="18e9a-115">Функция CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="18e9a-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="18e9a-116">Присваивает метки времени лицензии Authenticode XrML, созданной функцией CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="18e9a-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="18e9a-117">Функция CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="18e9a-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="18e9a-118">Проверяет правильность лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="18e9a-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="18e9a-119">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="18e9a-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="18e9a-120">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="18e9a-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="18e9a-121">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="18e9a-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="18e9a-122">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="18e9a-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e9a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="18e9a-123">See also</span></span>

- [<span data-ttu-id="18e9a-124">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="18e9a-124">Unmanaged API Reference</span></span>](../index.md)
