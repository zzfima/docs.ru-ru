---
title: Функция CertTimestampAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd77a8a81718837d55f3018564d0f4ba8fdc95ee
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44508547"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="157fb-102">Функция CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="157fb-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="157fb-103">Отметки времени для лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="157fb-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="157fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="157fb-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="157fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="157fb-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="157fb-106">[в] Подписанная лицензия Authenticode XrML, требующая отметки времени.</span><span class="sxs-lookup"><span data-stu-id="157fb-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="157fb-107">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="157fb-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="157fb-108">[в] URL-адресу сервера отметок времени.</span><span class="sxs-lookup"><span data-stu-id="157fb-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="157fb-109">[из] Указатель на CRYPT_DATA_BLOB для получения подписи с отметкой времени в кодировке base64.</span><span class="sxs-lookup"><span data-stu-id="157fb-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="157fb-110">Это обязанность вызывающего для освобождения `pTimestampSignatureBlob` -> `pbData` с `HepFree()` после использования.</span><span class="sxs-lookup"><span data-stu-id="157fb-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="157fb-111">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="157fb-111">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="157fb-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="157fb-112">Remarks</span></span>  
 <span data-ttu-id="157fb-113">Подпись с отметкой времени фактически представляет собой сообщение PKCS #7 SignedData, содержимое которого является двоичной формой SignatureValue из подписи лицензии.</span><span class="sxs-lookup"><span data-stu-id="157fb-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="157fb-114">По сути, она действует как подпись, подтверждающая лицензию.</span><span class="sxs-lookup"><span data-stu-id="157fb-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="157fb-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="157fb-115">Return Value</span></span>  
 <span data-ttu-id="157fb-116">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="157fb-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="157fb-117">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="157fb-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="157fb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="157fb-118">See Also</span></span>  
 [<span data-ttu-id="157fb-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="157fb-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
