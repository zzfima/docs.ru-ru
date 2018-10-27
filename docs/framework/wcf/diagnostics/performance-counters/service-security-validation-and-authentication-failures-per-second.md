---
title: 'Служба: количество сбоев при проверке безопасности и проверке подлинности в секунду'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: 97752fbd4ff38c40917c132fddfe3798a7ee6766
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183637"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="23799-102">Служба: количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="23799-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="23799-103">Имя счетчика: Security Validation and Authentication Failures Per Second.</span><span class="sxs-lookup"><span data-stu-id="23799-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="23799-104">Описание</span><span class="sxs-lookup"><span data-stu-id="23799-104">Description</span></span>  
 <span data-ttu-id="23799-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="23799-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="23799-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="23799-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="23799-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="23799-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="23799-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="23799-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="23799-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="23799-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="23799-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="23799-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="23799-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="23799-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="23799-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="23799-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="23799-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="23799-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="23799-114">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле</span><span class="sxs-lookup"><span data-stu-id="23799-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="23799-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="23799-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
