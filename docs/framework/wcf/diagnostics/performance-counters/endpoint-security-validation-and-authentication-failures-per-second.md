---
title: "Конечная точка: количество сбоев при проверке безопасности и проверке подлинности в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c6b50aa00fe59d0ad23d5ca0b77c7b89f97a0d1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="8bfd6-102">Конечная точка: количество сбоев при проверке безопасности и проверке подлинности в секунду</span><span class="sxs-lookup"><span data-stu-id="8bfd6-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="8bfd6-103">Имя счетчика: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="8bfd6-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="8bfd6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="8bfd6-104">Description</span></span>  
 <span data-ttu-id="8bfd6-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="8bfd6-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="8bfd6-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="8bfd6-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="8bfd6-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="8bfd6-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="8bfd6-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="8bfd6-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="8bfd6-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="8bfd6-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="8bfd6-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="8bfd6-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="8bfd6-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="8bfd6-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="8bfd6-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="8bfd6-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="8bfd6-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="8bfd6-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="8bfd6-114">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле:</span><span class="sxs-lookup"><span data-stu-id="8bfd6-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="8bfd6-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="8bfd6-115">(N1-N0)/((D1-D0)/F)</span></span>
