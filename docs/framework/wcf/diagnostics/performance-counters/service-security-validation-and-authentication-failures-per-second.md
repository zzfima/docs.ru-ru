---
title: "Служба: количество сбоев при проверке безопасности и проверке подлинности в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 85e6dae6b8358799370079c52c3d04e7c3221b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="e9f0e-102">Служба: количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="e9f0e-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="e9f0e-103">Имя счетчика: Security Validation and Authentication Failures Per Second.</span><span class="sxs-lookup"><span data-stu-id="e9f0e-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e9f0e-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="e9f0e-104">Description</span></span>  
 <span data-ttu-id="e9f0e-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="e9f0e-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="e9f0e-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="e9f0e-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="e9f0e-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="e9f0e-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="e9f0e-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="e9f0e-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="e9f0e-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="e9f0e-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="e9f0e-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e9f0e-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="e9f0e-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="e9f0e-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="e9f0e-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="e9f0e-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="e9f0e-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="e9f0e-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="e9f0e-114">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле</span><span class="sxs-lookup"><span data-stu-id="e9f0e-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="e9f0e-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e9f0e-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
