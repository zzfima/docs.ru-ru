---
title: 'Конечная точка: количество сбоев при проверке безопасности и проверке подлинности'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8c46354fac11f5f0b46ef1b5629157f6da455fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="ff6e8-102">Конечная точка: количество сбоев при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="ff6e8-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="ff6e8-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="ff6e8-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="ff6e8-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ff6e8-104">Description</span></span>  
 <span data-ttu-id="ff6e8-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="ff6e8-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ff6e8-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="ff6e8-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="ff6e8-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="ff6e8-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="ff6e8-108">Токен клиента не прошел проверку подлинности (неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="ff6e8-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="ff6e8-109">Сбой при проверке подписи (сообщение было изменено).</span><span class="sxs-lookup"><span data-stu-id="ff6e8-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="ff6e8-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="ff6e8-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="ff6e8-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="ff6e8-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="ff6e8-112">В сообщении отсутствуют некоторые обязательные элементы (отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="ff6e8-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="ff6e8-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="ff6e8-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
