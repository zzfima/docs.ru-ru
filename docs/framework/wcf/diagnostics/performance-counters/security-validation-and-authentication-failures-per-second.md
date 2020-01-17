---
title: Количество сбоев при проверке безопасности и проверке подлинности в секунду
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: 546d81b73e912915d265fb194de4ad9e45d55cea
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163921"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="d57d7-102">Количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="d57d7-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="d57d7-103">Имя счетчика: Security Validation and Authentication Failures Per Second.</span><span class="sxs-lookup"><span data-stu-id="d57d7-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d57d7-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d57d7-104">Description</span></span>  
 <span data-ttu-id="d57d7-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="d57d7-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="d57d7-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="d57d7-106">Such problems include:</span></span>  
  
- <span data-ttu-id="d57d7-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="d57d7-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="d57d7-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="d57d7-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="d57d7-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="d57d7-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="d57d7-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="d57d7-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="d57d7-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="d57d7-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="d57d7-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="d57d7-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="d57d7-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="d57d7-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="d57d7-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span><span class="sxs-lookup"><span data-stu-id="d57d7-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="d57d7-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="d57d7-115">(N1-N0)/((D1-D0)/F)</span></span>
