---
title: 'Конечная точка: Количество сбоев при проверке безопасности и проверке подлинности в секунду'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: 43886f79585fb9a63eeb51360cc869365c100a1d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129055"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="5ed37-102">Конечная точка: Количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="5ed37-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="5ed37-103">Имя счетчика: Количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="5ed37-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="5ed37-104">Описание</span><span class="sxs-lookup"><span data-stu-id="5ed37-104">Description</span></span>  
 <span data-ttu-id="5ed37-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="5ed37-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="5ed37-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="5ed37-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="5ed37-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="5ed37-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="5ed37-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="5ed37-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="5ed37-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="5ed37-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="5ed37-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5ed37-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="5ed37-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="5ed37-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="5ed37-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="5ed37-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="5ed37-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="5ed37-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="5ed37-114">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле:</span><span class="sxs-lookup"><span data-stu-id="5ed37-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="5ed37-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="5ed37-115">(N1-N0)/((D1-D0)/F)</span></span>
