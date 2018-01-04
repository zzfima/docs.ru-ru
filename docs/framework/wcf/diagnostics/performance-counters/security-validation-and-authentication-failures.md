---
title: "Сбои при проверке безопасности и проверке подлинности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c52b54d2be2e824de478e0ee9ec2452c57e181b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="890f8-102">Сбои при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="890f8-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="890f8-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="890f8-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="890f8-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="890f8-104">Description</span></span>  
 <span data-ttu-id="890f8-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="890f8-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="890f8-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="890f8-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="890f8-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="890f8-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="890f8-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="890f8-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="890f8-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="890f8-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="890f8-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="890f8-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="890f8-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="890f8-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="890f8-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="890f8-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="890f8-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="890f8-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
