---
title: Количество сбоев при проверке безопасности и проверке подлинности в секунду
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: e3db8cb20399bdff9b73a428ea2a53909da4eee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915776"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="50afc-102">Количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="50afc-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="50afc-103">Имя счетчика: При проверке безопасности и сбои проверки подлинности в секунду.</span><span class="sxs-lookup"><span data-stu-id="50afc-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="50afc-104">Описание</span><span class="sxs-lookup"><span data-stu-id="50afc-104">Description</span></span>  
 <span data-ttu-id="50afc-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="50afc-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="50afc-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="50afc-106">Such problems include:</span></span>  
  
- <span data-ttu-id="50afc-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="50afc-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="50afc-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="50afc-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="50afc-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="50afc-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="50afc-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="50afc-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="50afc-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="50afc-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="50afc-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="50afc-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="50afc-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="50afc-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="50afc-114">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле:</span><span class="sxs-lookup"><span data-stu-id="50afc-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="50afc-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="50afc-115">(N1-N0)/((D1-D0)/F)</span></span>
