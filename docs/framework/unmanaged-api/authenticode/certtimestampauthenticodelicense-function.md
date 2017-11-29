---
title: "Функция CertTimestampAuthenticodeLicense"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertTimestampAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ec863e9accbd2156b6eeed5857ff86075cf0a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="65810-102">Функция CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="65810-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="65810-103">Отметки времени для лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="65810-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65810-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65810-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65810-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65810-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="65810-106">[в] Подписанная лицензия Authenticode XrML, требующая отметки времени.</span><span class="sxs-lookup"><span data-stu-id="65810-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="65810-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="65810-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="65810-108">[в] URL-адресу сервера отметок времени.</span><span class="sxs-lookup"><span data-stu-id="65810-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="65810-109">[из] Указатель на CRYPT_DATA_BLOB для получения подписи с отметкой времени в кодировке base64.</span><span class="sxs-lookup"><span data-stu-id="65810-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="65810-110">Это вызывающим для освобождения `pTimestampSignatureBlob` -> `pbData` с `HepFree()` после использования.</span><span class="sxs-lookup"><span data-stu-id="65810-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="65810-111">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="65810-111">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65810-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="65810-112">Remarks</span></span>  
 <span data-ttu-id="65810-113">Подпись с отметкой времени фактически представляет собой сообщение PKCS #7 SignedData, содержимое которого является двоичной формой SignatureValue из подписи лицензии.</span><span class="sxs-lookup"><span data-stu-id="65810-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="65810-114">По сути, она действует как подпись, подтверждающая лицензию.</span><span class="sxs-lookup"><span data-stu-id="65810-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65810-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65810-115">Return Value</span></span>  
 <span data-ttu-id="65810-116">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="65810-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="65810-117">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="65810-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65810-118">См. также</span><span class="sxs-lookup"><span data-stu-id="65810-118">See Also</span></span>  
 [<span data-ttu-id="65810-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="65810-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
